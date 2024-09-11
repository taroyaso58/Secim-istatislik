using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
using System.Data.SqlClient;

namespace Seçim_ve_İstatislik_Uygulaması
{
    public partial class Secim : Form
    {
        public Secim()
        {
            InitializeComponent();
        }

        SqlConnection baglanti = new SqlConnection(@"Data Source= /* Kendi veri tabanı bağlantın */ ;Initial Catalog=Secim&Istatislik;Integrated Security=True");
        private void btn_oygirisi_Click(object sender, EventArgs e)
        {
            // Oy Girişi sağlama 
            baglanti.Open();
            SqlCommand cmd = new SqlCommand("insert into Ilceler (IlceIsim,AParti,BParti,CParti,DParti,EParti) values (@p1,@p2,@p3,@p4,@p5,@p6)", baglanti);
                /* Değerleri Almaya yarar */
            cmd.Parameters.AddWithValue("@p1", txt_ilcead.Text);
            cmd.Parameters.AddWithValue("@p2", txt_aparti.Text);
            cmd.Parameters.AddWithValue("@p3", txt_bparti.Text);
            cmd.Parameters.AddWithValue("@p4", txt_cparti.Text);
            cmd.Parameters.AddWithValue("@p5", txt_dparti.Text);
            cmd.Parameters.AddWithValue("@p6", txt_eparti.Text);
            cmd.ExecuteNonQuery();
            baglanti.Close();
            MessageBox.Show("İşleminiz gerçekleşmiştir");
        }

        private void btn_grafikler_Click(object sender, EventArgs e)
        {
                /* Formlar arası geçiş */
            FrmGrafikler frmGrafikler = new FrmGrafikler();
            frmGrafikler.ShowDialog();
            this.Close();
        }

        private void btn_cikis_Click(object sender, EventArgs e)
        {
                /* Çıkış Yapma*/
            Close();
        }
    }
}
