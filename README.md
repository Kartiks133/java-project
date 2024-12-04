import java.util.*;
import java.time.format.DateTimeFormatter;  
import java.time.LocalDateTime; 
import java.text.SimpleDateFormat;
import javax.swing.*;  
import java.awt.event.*; 
import java.awt.*;
import java.applet.*;  
import javax.swing.JPanel;

public class Bank_GUI implements ActionListener 
{
JButton Open_Account,Deposit,Withdraw,Statement,Fixed_Deposit,b,exit;             
    JTextField User_Name,DOB,Adhaar,Phn,Addrs,Pswrd;
    String name=null,password="",address=null,DateOfBirth=null,pswrd="",adhar=null;
    String PhnNo=null;
    Font  f4  = new Font(Font.DIALOG,  Font.BOLD, 25);
    Font  f5 = new Font("Comic Sans MS", Font.PLAIN, 15);
    long amt=0,amtW=0,intrest=0,amtFD=0,Fdfinal=0;
long ACTNO,amtd;
int check=0;
String AccountNo=null;
JFrame J_Main;
Bank_GUI(){

        
             try {
    for (UIManager.LookAndFeelInfo info : UIManager.getInstalledLookAndFeels()) {
        if ("Nimbus".equals(info.getName())) {
            UIManager.setLookAndFeel(info.getClassName());
            break;
        }
    }
} catch (Exception e) {
    // If Nimbus is not available, you can set the GUI to another look and feel.
}
//Defining buttons

             b=new JButton("ENTER");
             exit=new JButton("Exit");
             Open_Account=new JButton("Open Account");
             Deposit=new JButton("Deposit");
             Withdraw=new JButton("Withdraw");
             Statement=new JButton("Bank Statement");
             Fixed_Deposit=new JButton("Fixed Deposit");  
             //font of buttons
             
             Open_Account.setFont(f4);
             Deposit.setFont(f4);
             Withdraw.setFont(f4);
             Statement.setFont(f4);
             Fixed_Deposit.setFont(f4);
             exit.setFont(f4);
             //main jframe
             J_Main= new JFrame("BANK");
             J_Main.setVisible(true);  
             J_Main.setSize(800,600); 
             J_Main.setLocationRelativeTo(null); 
             J_Main.setResizable(false);
             //Main panel
             JPanel JP=new JPanel(new GridLayout(2,2,20,20));
             //adding buttons
             JP.add(Open_Account);
             JP.add(Deposit);
             JP.add(Withdraw);
             JP.add(Statement);
             JP.add(Fixed_Deposit);
             JP.add(exit);
             //adding panel
             J_Main.add(JP);
             
             Open_Account.addActionListener(this);  
             Deposit.addActionListener(this);
             Withdraw.addActionListener(this);  
             Statement.addActionListener(this);
             Fixed_Deposit.addActionListener(this); 
             exit.addActionListener(this); 
             b.addActionListener(this); 
                }
            
            
public static void main(String[] args) { 
    
            //long ACTNO = (long) Math.floor(Math.random() * 9_000_000_000L) + 1_000_000_000L;
            new Bank_GUI();
           
              
}


 public void actionPerformed(ActionEvent e) {
   
        //look and feel
           try {
    for (UIManager.LookAndFeelInfo info : UIManager.getInstalledLookAndFeels()) {
        if ("Nimbus".equals(info.getName())) {
            UIManager.setLookAndFeel(info.getClassName());
            break;
        }
    }
} catch (Exception c) {
    // If Nimbus is not available, you can set the GUI to another look and feel.

}

 if(e.getSource()==Open_Account){
     amt=0;
    //Open Account Section
        JButton b;
        JFrame J_Account= new JFrame("Open Account");
        JPanel JA=new JPanel(new GridLayout(6,1,10,50));
        J_Account.setVisible(true);
        JA.setBorder( BorderFactory.createEmptyBorder(20,20,20,20) );
        J_Account.setSize(800,600); 
        J_Account.setResizable(false);
        J_Account.setLocationRelativeTo(null); 
        JTextField tf=new JTextField(10);
        J_Account.add(tf);
        tf.setVisible(true);
        JLabel l1,l2,l3,l4,l5,l6;
        
        
        l1=new JLabel("Enter your name:");
        l2=new JLabel("Enter your Date Of Birth:");         
        l3=new JLabel("Enter your aadhar number:");
        l4=new JLabel("Enter your phone number:");
        l5=new JLabel("Enter your address:");
        l6=new JLabel("Set a password:");
        l1.setFont(f5);
        l2.setFont(f5);
        l3.setFont(f5);
        l4.setFont(f5);
        l5.setFont(f5);
        l6.setFont(f5);
        User_Name=new JTextField(10);
        JPasswordField passwordField = new JPasswordField(10);
        DOB=new JTextField(10);
        Adhaar=new JTextField(10);
        Phn=new JTextField(10);
        Addrs=new JTextField(10);
        User_Name.setFont(f5);
        passwordField.setFont(f5);
        DOB.setFont(f5);
        Adhaar.setFont(f5);
        Phn.setFont(f5);
        Addrs.setFont(f5);
        J_Account.add(JA);
        JA.add(l1);
        JA.add(User_Name);
        JA.add(l2);
        JA.add(DOB);
        JA.add(l3);
        JA.add(Adhaar);
        JA.add(l4);
        JA.add(Phn);
        JA.add(l5);
        JA.add(Addrs);
        JA.add(l6);
        JA.add(passwordField);
        JPanel pn = new JPanel();
        pn.setPreferredSize(new Dimension(60, 70));
        J_Account.add( pn , BorderLayout.SOUTH);
        b=new JButton("ENTER");
        
        b.setPreferredSize(new Dimension(70,30));     
        pn.add(b);  
         
         
            b.addActionListener(new ActionListener(){  
    public void actionPerformed(ActionEvent enter){ 
        
        if(User_Name.getText().isEmpty() || DOB.getText().isEmpty() || Adhaar.getText().isEmpty() ||Phn.getText().isEmpty() ||  Addrs.getText().isEmpty()||passwordField.getText().isEmpty())
        {
            JOptionPane.showMessageDialog(null,"one or more fileds are empty");
        }
        else
        {
            ACTNO = (long) Math.floor(Math.random() * 9_000_000_000L) + 1_000_000_000L;
         String AccountNo=Long.toString(ACTNO);
        User_Name.setEditable(false);
        DOB.setEditable(false);
        Adhaar.setEditable(false);
        Phn.setEditable(false);
        Addrs.setEditable(false);  
        b.setEnabled(false);
        passwordField.setEditable(false);
        password=passwordField.getText();
        name=User_Name.getText();
        DateOfBirth=DOB.getText();
        adhar=Adhaar.getText();
        PhnNo=Phn.getText();
        address=Addrs.getText(); 
        JOptionPane.showMessageDialog(null,"Account Cretaed Successfully!!");
         JOptionPane.showMessageDialog(null,"Your account number:"+ACTNO);
        J_Account.dispose();
        }
        
       
        
    }  
    
    });
    
        
        

 
    }
    else if(e.getSource()==Deposit){
        
       JFrame J_deposit= new JFrame("Deposit");
       JPanel JW=new JPanel(new GridLayout(2,1,10,200));
       JW.setBorder( BorderFactory.createEmptyBorder(70,40,70,40) );
        J_deposit.setVisible(true);
        J_deposit.setSize(800,600); 
        J_deposit.setLocationRelativeTo(null);
        J_deposit.add(JW);
        J_deposit.setResizable(false);
        JLabel Damt;
        Damt=new JLabel("Enter amount to be deposited:");
        JTextField DAMT=new JTextField(10);
        JLabel ACT=new JLabel("Enter account number:");
        JTextField Acno=new JTextField(10);
         Damt.setFont(f5);
         DAMT.setFont(f5);
         ACT.setFont(f5);
         Acno.setFont(f5);
        JW.add(Damt);
        JW.add(DAMT);
        JW.add(ACT);
        JW.add(Acno);
        JPanel pn=new JPanel();
        
        pn.setBorder( BorderFactory.createEmptyBorder(50,50,50,50) );    
          
        J_deposit.add( pn , BorderLayout.SOUTH);
        JButton b=new JButton("ENTER");
        pn.add(b,BorderLayout.CENTER);
         b.addActionListener(new ActionListener(){  
    public void actionPerformed(ActionEvent enter){ 
        
        
       
    if(DAMT.getText().isEmpty()||Acno.getText().isEmpty()){
        JOptionPane.showMessageDialog(null,"one or more fileds are empty");
    }
    else{
         try {
            
        long d = Long.parseLong(DAMT.getText());
        
    } catch (NumberFormatException nfe) {
        JOptionPane.showMessageDialog(null,"Please enter a valid deposit amount");
        
    }Long g=Long.parseLong(Acno.getText());
    if(g==ACTNO){
        amtd=Long.parseLong(DAMT.getText());
        amt+=amtd;
        Acno.setEditable(false);
        DAMT.setEditable(false);
        JOptionPane.showMessageDialog(null,"Amount Deposited Successfully");
        J_deposit.dispose();
    }
    else{
        JOptionPane.showMessageDialog(null,"invalid entry");
    }
    
}
}
});
    }else if(e.getSource()==Withdraw){
       JFrame J_withdraw= new JFrame("Withdraw");
        J_withdraw.setVisible(true);
        J_withdraw.setSize(800,600); 
        J_withdraw.setResizable(false);
        J_withdraw.setLocationRelativeTo(null);
        JLabel lwamt=new JLabel("Enter Amount:");
        JLabel lacc=new JLabel("Enter Account Number:");
        JLabel lpwd=new JLabel("Enter Password:");
        JTextField WAMT=new JTextField(10);
        JTextField ACC=new JTextField(10);
         JPasswordField PWD = new JPasswordField(10);
        JPanel JWTH=new JPanel(new GridLayout(3,1,10,150));
        JWTH.setBorder( BorderFactory.createEmptyBorder(40,40,40,40) );
        J_withdraw.add(JWTH);
        JWTH.add(lwamt);
        JWTH.add(WAMT);
        JWTH.add(lacc);
        JWTH.add(ACC);
        JWTH.add(lpwd);
        JWTH.add(PWD);
        lwamt.setFont(f5);
        WAMT.setFont(f5);
        lacc.setFont(f5);
        ACC.setFont(f5);
        lpwd.setFont(f5);
        PWD.setFont(f5);
        JPanel pn=new JPanel();
        //pn.setPreferredSize(new Dimension(60, 250));
        pn.setBorder( BorderFactory.createEmptyBorder(10,10,10,10) );    
        JButton b=new JButton("ENTER");
        J_withdraw.add( pn , BorderLayout.SOUTH);
        pn.add(b,BorderLayout.CENTER);
       
          b.addActionListener(new ActionListener(){  
    public void actionPerformed(ActionEvent enter){ 
         try {
            
        long dd = Long.parseLong(WAMT.getText());
        
    } catch (NumberFormatException ne) {
        
        JOptionPane.showMessageDialog(null,"Please enter a valid amount");
    }
    long ll=Long.parseLong(ACC.getText());
    if(WAMT.getText().isEmpty()||ACC.getText().isEmpty()||PWD.getText().isEmpty()){
        JOptionPane.showMessageDialog(null,"One or more fileds are empty");
    }
    else{
        if(ll==ACTNO && password.compareTo(PWD.getText())==0){
            amtW=Long.parseLong(WAMT.getText());
            if(amt-amtW>=500){
                amt-=amtW;
                 JOptionPane.showMessageDialog(null,"Amount Withdrawn Successfully");
                 WAMT.setEditable(false);
                 ACC.setEditable(false);
                 J_withdraw.dispose();
            }
            else{
                 JOptionPane.showMessageDialog(null,"Low Balance");
            }
        }
        else{
             JOptionPane.showMessageDialog(null,"Invalid Entries");
        }
    }
    }
});
        
      }
    else if(e.getSource()==Statement){
       JFrame J_statement= new JFrame("Bank Statement");
        J_statement.setVisible(true);
        J_statement.setSize(800,600); 
        J_statement.setResizable(false);
        J_statement.setLocationRelativeTo(null);
        JLabel Name,Addrs,ACC,BALAMT,heading;
        Name=new JLabel("NAME=>");
        Addrs=new JLabel("ADDRESS=>");
        ACC=new JLabel("ACCOUNT NUMBER=>");
        BALAMT=new JLabel("BALANCE AMOUNT=>");
        Name.setFont(f5);
        Addrs.setFont(f5);
        ACC.setFont(f5);
        BALAMT.setFont(f5);
        JTextField nm,ads,accn,bal;
        
        nm=new JTextField(name);
        ads=new JTextField(address);
        String acn=ACTNO+"";
        accn=new JTextField(acn);
        String bmt=amt+"";
        bal=new JTextField(bmt);
        nm.setFont(f5);
        ads.setFont(f5);
        bal.setFont(f5);
        accn.setFont(f5);
        nm.setEditable(false);
        accn.setEditable(false);
        ads.setEditable(false);
        bal.setEditable(false);
        heading=new JLabel("BANK STATEMENT");
        JPanel Statement=new JPanel();
        J_statement.add( Statement, BorderLayout.NORTH);
        Statement.add(heading);
        JPanel secnd=new JPanel(new GridLayout(4,2,10,70));
        secnd.setBorder( BorderFactory.createEmptyBorder(70,40,70,40) ); 
        J_statement.add( secnd, BorderLayout.CENTER);
        secnd.add(Name);
        secnd.add(nm);
        secnd.add(ACC);
        secnd.add(accn);
        secnd.add(Addrs);
        secnd.add(ads);
        secnd.add(BALAMT);
        secnd.add(bal);
        JButton b=new JButton("CLOSE");
        JPanel pn=new JPanel();
        J_statement.add( pn, BorderLayout.SOUTH);
        pn.add(b);
        b.addActionListener(new ActionListener(){  
    public void actionPerformed(ActionEvent enter){ 
        J_statement.dispose();
    }
});
    }else if(e.getSource()==Fixed_Deposit){
      
       JFrame J_fd= new JFrame("Fixed Deposit");
        J_fd.setVisible(true);
        J_fd.setSize(800,600); 
        J_fd.setLocationRelativeTo(null);
        J_fd.setResizable(false);
      JPanel fix=new JPanel(new GridLayout(5,2,10,70));
       JLabel lAcc=new JLabel("Account Number:");
       JLabel lpwd=new JLabel("Password:");
       JLabel FdAMT=new JLabel("Amount:");
       JLabel lTime=new JLabel("Duration(in years):");
      JTextField TAcc=new JTextField(10);
      JPasswordField TPwd=new JPasswordField(10);
      JTextField Tamt=new JTextField(10);
      JTextField Ttime=new JTextField(10);
        
                     J_fd.add(fix);
                     fix.add(lAcc);
                     fix.add(TAcc);
                     fix.add(lpwd);
                     fix.add(TPwd);
                     fix.add(FdAMT);
                     fix.add(Tamt);
                     fix.add(lTime);
                     fix.add(Ttime);
                     fix.setVisible(true);
                     J_fd.add(fix);
                     lAcc.setFont(f5);
                     TAcc.setFont(f5);
                     lpwd.setFont(f5);
                     TPwd.setFont(f5);
                     FdAMT.setFont(f5);
                     Tamt.setFont(f5);
                     lTime.setFont(f5);
                     Ttime.setFont(f5);
                      SimpleDateFormat DateFormat
                      
                    = new SimpleDateFormat("MM/dd/yyyy");
     
                Calendar calendar = Calendar.getInstance();
                 JPanel pn=new JPanel();
            JButton b=new JButton("Enter");
            
            pn.add(b);
            pn.setBorder( BorderFactory.createEmptyBorder(40,40,40,40) ); 
            J_fd.add(pn,BorderLayout.SOUTH);
            
                 
                      b.addActionListener(new ActionListener(){  
    public void actionPerformed(ActionEvent enter){ 
         try {
            
        long f = Long.parseLong(Tamt.getText());
        
    } catch (NumberFormatException nfe) {
        JOptionPane.showMessageDialog(null,"Please enter a valid deposit amount");
    }
try {
            
        int tt = Integer.parseInt(Ttime.getText());
        
    } catch (NumberFormatException ne) {
        JOptionPane.showMessageDialog(null,"Please enter a valid duration");
    }
        if(TAcc.getText().isEmpty()||TPwd.getText().isEmpty()||Tamt.getText().isEmpty()||Ttime.getText().isEmpty()){
             JOptionPane.showMessageDialog(null,"One or more fields empty");
        }
        else{
            
        long ll=Long.parseLong(TAcc.getText());
                     int t=Integer.parseInt(Ttime.getText());
                     
                     if(ll==ACTNO&&TPwd.getText().compareTo(password)==0){
                     amtFD=Long.parseLong(Tamt.getText());
                        if(amt-amtFD>=500){
                        
                        amt-=amtFD;
                        calendar.add(Calendar.YEAR, t);
                         String m_date = DateFormat.format(calendar.getTime());
           
           
                        if(t==1){
                            intrest=(amtFD*4*t)/100;
                        }
                        else if(t==2){
                            intrest=(amtFD*5*t)/100;
                        }
                        else if(t==3){
                            intrest=(amtFD*6*t)/100;
                        }
                        else if(t==4){
                            intrest=(amtFD*7*t)/100;
                        }
                        else if(t>=5){
                            intrest=(amtFD*8*t)/100;
                        }
                        Fdfinal=amtFD+intrest;
                        JFrame disp=new JFrame("Fixed Deposit");
                    disp.setSize(800,600);
                    disp.setResizable(false);
                    disp.setVisible(true);
                    disp.setLocationRelativeTo(null);
                     JLabel heading=new JLabel("FIXED DEPOSIT");
                     heading.setFont(f4);
                     JPanel head=new JPanel();
                     disp.add(head,BorderLayout.NORTH);
                     head.add(heading);
                     JLabel MDate=new JLabel("Maturity Date=>");
                     JLabel MValue=new JLabel("Maturity Amount=>");
                     MValue.setFont(f5);
                     MDate.setFont(f5);
                     JTextField MD=new JTextField(m_date);
                     String fin=Fdfinal+"";
                     JTextField MV=new JTextField(fin);
                     JPanel findisp=new JPanel(new GridLayout(2,2,10,290));
                     findisp.setBorder( BorderFactory.createEmptyBorder(70,40,70,40) ); 
                     disp.add(findisp, BorderLayout.CENTER);
                     MD.setFont(f5);
                     MV.setFont(f5);
                     findisp.add(MDate); 
                     findisp.add(MD);
                     findisp.add(MValue);
                     findisp.add(MV);
                     MD.setEditable(false);
                     MV.setEditable(false);
                     JPanel dn=new JPanel();
                     JButton b=new JButton("CLOSE");
                     disp.add(dn,BorderLayout.SOUTH);
                     dn.add(b);
                       b.addActionListener(new ActionListener(){  
    public void actionPerformed(ActionEvent enter){ 
        disp.dispose();
        J_fd.dispose();
    }
});
                    }
                    else{
                        JOptionPane.showMessageDialog(null,"Insufficient Funds");
                    }
                    
                    
                     }
                     else{
                          JOptionPane.showMessageDialog(null,"Invalid Entry");
                     }
                    }
                    }
                });
                }
        else if(e.getSource()==exit){
           J_Main.dispose();
        }
 }
}# java-project
