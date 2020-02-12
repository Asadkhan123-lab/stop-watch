# stop-watch
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace stop_watch
{
    public partial class Form1 : Form
    {
        int millisec;
        int seconds;
        int minutes;
        public Form1()

        {
            InitializeComponent();
            rstbtn.Enabled = true;

        }
       
       

        private void timer1_Tick(object sender, EventArgs e)
        {
            millisec++;
            if (millisec == 100)
            {
                seconds++;
                millisec = 0;

                if (seconds == 60)
                {
                    minutes++;
                    seconds = 0;

                    if (minutes == 60)
                    {

                    }
                }
            }
            lblmnt.Text = minutes.ToString() + ":"; lblmili.Text = millisec.ToString() + ":"; lblsec.Text = seconds.ToString() + ":";
        }

        private void button1_Click(object sender, EventArgs e)
        {
            timer1.Start();
            startbtn.Enabled = true;
              millisec++;
              startbtn.BackColor = Color.DarkTurquoise;
              stopbtn.BackColor = Color.OldLace;
              rstbtn.BackColor = Color.OldLace;
              
         }
        
        private void button2_Click(object sender, EventArgs e)
        {
            timer1.Stop();
            stopbtn.Enabled = true;
            
            stopbtn.BackColor = Color.DarkTurquoise;
            rstbtn.BackColor = Color.OldLace;
            startbtn.BackColor = Color.OldLace;
        }

            private void button3_Click(object sender, EventArgs e)
        {
          
          /*  minutes=0;
           seconds=0;
           milisecond=0;*/
            lblmili.Text = "0";
            lblmnt.Text = "0";
            lblsec.Text = "0";
            rstbtn.Enabled = true;
            
            rstbtn.BackColor = Color.DarkTurquoise;
            startbtn.BackColor = Color.OldLace;
            stopbtn.BackColor = Color.OldLace;


        }
    }
}
