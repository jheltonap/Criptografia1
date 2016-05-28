using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace WindowsFormsApplication26
{
     class Codigo
    {
        public string caracteres = "!@#$%¨&*()_-+{}[]abcdefghijklmnopqrstuvwxyz0123456789";
        public string novotexto;
        public string escolha;

        public string Codidificar(string texto,int chave)
        {
            char[] caractereschar = caracteres.ToCharArray();
            char[] textochar = texto.ToCharArray();

                for (int i = 0; i < textochar.Length; i++)
                {
                    for (int n = 0; n < caractereschar.Length; n++)
                    {
                        if (textochar[i] == caractereschar[n])
                        {
                            if ((n + chave) <= (caractereschar.Length - 1))
                            {
                                novotexto += caractereschar[n + chave];
                            }
                            else
                            {
                                novotexto += caractereschar[(n + chave) - (caractereschar.Length)];
                            }
                        }
                    }
                }

                return novotexto;
            }



        public string Decodificar(string texto, int chave)
        {
            char[] caractereschar = caracteres.ToCharArray();
            char[] textochar = texto.ToCharArray();

            for (int i = 0; i < textochar.Length; i++)
            {
                for (int n = 0; n < caractereschar.Length; n++)
                {
                    if (textochar[i] == caractereschar[n])
                    {
                        if ((n - chave) < 0)
                        {
                            novotexto += caractereschar.Length + 1;
                        }
                        else
                        {
                            novotexto += caractereschar[(n - chave)];
                        }
                    }
                }
            }

            return novotexto;
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

namespace WindowsFormsApplication26
{
    public partial class Form1 : Form
    {
        Codigo[] codigo;
        string novoTexto;
        public Form1()
        {
            InitializeComponent();
        }

        public void Form1_Load(object sender, EventArgs e)
        {
            codigo = new Codigo[2];
            codigo[0] = new Codigo();
            codigo[1] = new Codigo();
            codigo[0].escolha = "Criptografar";
            codigo[1].escolha = "Descriptografar";

            foreach (Codigo codigo in codigo)
            {
                comboBox1.Items.Add(codigo.escolha);
            }
        }
   

        public void comboBox1_SelectedIndexChanged(object sender, EventArgs e)
        {
            int Indice = comboBox1.SelectedIndex;
            Codigo indiceSelecionado = codigo[Indice];
            textBox1.Focus();

            if (Indice == 0)
            {
                novoTexto = indiceSelecionado.Codidificar(textBox1.Text, Convert.ToInt16(textBox2.Text));
                textBox3.Text = novoTexto;
            }
            else
            {
                novoTexto = indiceSelecionado.Decodificar(textBox1.Text, Convert.ToInt16(textBox2.Text));
                textBox3.Text = novoTexto;

            }
        } 
    }
}
