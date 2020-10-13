# TheCashier
Aplikasi ini dapat menghitung nilai pembelian barang/jasa. jadi memudahkan anda dalam pekerjaan dibidang cashier.

#Fungsionalitas
- user dapat memasukan huruf dan angka
- user dapat menekan tombol hitung
-user dapat mengetahui total pembelanjaan
-user dapat melihat apa saja yang dibeli

#How does it works?
diawali dari method:
'''csharp
 public partial class MainWindow : Window
    {
        private Calculator calculator;
        public MainWindow()
        {
            InitializeComponent();
            calculator = new Calculator();
            listBox.ItemsSource = calculator.getlistItem();
        }

        private void AddButton_Click(object sender, RoutedEventArgs e)
        {
            string title = itemNameBox.Text;
            int quantity = int.Parse(quantityBox.Text);
            string type = typeBox.Text;
            double price = double.Parse(priceBox.Text);

            Item item = new Item(new Random(). Next(), title, quantity, price, price, type);
            calculator.addItem(item);
            double total = calculator.getTotal();

            totalLabel.Content = String.Format("Rp. {0}", total);

            listBox.Items.Refresh();
        }
        '''
        logika terdapat pada class items.cs atau sebagai berikut:
        '''chasrp
         public double getSubTotal(int v)
        {
            subtotal = price * quantity;
            return subtotal;
        }
        '''
        dan cara kerjanya, untuk mendapatkan subtotal itu price dikali dengan quantity
