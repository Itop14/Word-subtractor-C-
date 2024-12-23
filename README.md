# Word-subtractor-C#

This program takes two strings. Which it then converts to ASCII values and subtracts from one another. Additionally, there is a function that removes any character in the second word that occurs in the first word and the other way around.


    using System;
    using System.Collections.Generic;
    using System.ComponentModel;
    using System.Data;
    using System.Drawing;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    using System.Windows.Forms;
    
    namespace Word_subtractor
    {
        public partial class Form1 : Form
        {
            public Form1()
            {
                InitializeComponent();
            }
    
            private void Subtract_btn_Click(object sender, EventArgs e)
            {
                int asciivalue = 0;
                int asciitotal = 0;
                
                string firstword = first_word.Text;
    
                foreach (char letter in firstword)
                {
                    asciivalue = Convert.ToInt32(letter);
                    asciitotal = asciitotal + asciivalue;
                }
    
                int asciivalue2 = 0;
                int asciitotal2 = 0;
    
                string secondword = second_word.Text;
                
                foreach (char letter in secondword)
                {
                    asciivalue2 = Convert.ToInt32(letter);
                    asciitotal2 = asciitotal2 + asciivalue2;
                }
                ans_label.Text = (asciitotal - asciitotal2).ToString();
            }
    
            private void Cut_btn_Click(object sender, EventArgs e)
            {
                string firstword = first_word.Text;
                string secondword = second_word.Text;
    
                string result = "";
    
                foreach (char letter in firstword)
                {
                    if (!secondword.Contains(letter)) 
                    {
                        result += letter; 
                    }
                }
    
                string result2 = "";
    
                foreach (char letter in secondword)
                {
                    if (!firstword.Contains(letter)) 
                    {
                        result2 += letter; 
                    }
                }
    
                first_word.Text = result;
                second_word.Text = result2;
    
            }
        }
    }
