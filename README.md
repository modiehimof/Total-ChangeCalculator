# Total-ChangeCalculator
new repo
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace CreativeIdoLast
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void btnReady_Click(object sender, EventArgs e)
        {
            Form2 myForm = new Form2();
            myForm.Show();
        }

        private void btnClose_Click(object sender, EventArgs e)
        {
            this.Close();
        }
    }
}

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace CreativeIdoLast
{
    public partial class Form2 : Form
    {
        public Form2()
        {
            InitializeComponent();
        }

        public double CONST = 1.15;

 

        private void btnCalculate_Click(object sender, EventArgs e)
        {
            if (rdChange.Checked)
            {
                MessageBox.Show("You chose to calculate change!");
                MessageBox.Show("Your change is : R" + calcChange());
            }
            else
            {
                MessageBox.Show("You chose to calculate the total!");
                MessageBox.Show("Your total is : R" + CalcTotal());
            }
        }
        public double CalcTotal()
        {
            double item1 = double.Parse(txtItem1.Text);
            double item2 = double.Parse(txtItem2.Text);
            double item3 = double.Parse(txtItem3.Text);

            double total = item1 + item2 + item3 * CONST;
            return total;
        }
        public double AmountPaid()
        {
            double AmountPaid = double.Parse(txtAmountPaid.Text);
            return AmountPaid;
        }

        public double calcChange()
        {
            return AmountPaid() - CalcTotal();
        }

        private void btnExit_Click(object sender, EventArgs e)
        {
            this.Close();
        }
    }
}
