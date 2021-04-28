# Tugas_Database_SQFLITE
import 'package:flutter/material.dart';
void main() => runApp(App());

class App extends StatelessWidget {
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter data perpustakaan',
      home: Scaffold(
        appBar: AppBar(
          title: Text('6SIA10'),
        ),
        body: Buku(),
      ),
    );
  }
}

class DataBuku{
  
  String namabuku;
  String jumlah;
  String penerbit;
  
  
  DataBuku({ this.namabuku, this.jumlah, this.penerbit});
  
}

// class Buku
class Buku extends StatefulWidget {
  _MyappState createState() => _MyappState();
}

class _MyappState extends State<Buku> {
  //deklarasi variabel
  final txtnamabuku = TextEditingController();
  final txtthnterbit = TextEditingController();
  

  List<Widget> data = [];

  onTambah() {
    setState(() {
      data.add(ListTile(
        leading: Text(txtthnpenerbit.text),
        title: Text(txtnamabuku.text),
        subtitle: Text(txtjumlah.text),
        trailing: Text(txtpenerbit.text),
      ));
      txtnamabuku.clear();
      txtjumlah.clear();
      txtpenerbit.clear();
      txtthnterbit.clear();
    });
  }

  Widget build(BuildContext context) {
    return ListView(
      children: <Widget>[
        new Container(
          padding: EdgeInsets.all(10.0),
          child: Column(
            mainAxisAlignment: MainAxisAlignment.spaceEvenly,
            children: <Widget>[
           
              TextField(
                controller: txtnamabuku,
                decoration: InputDecoration(hintText: 'Nama Buku'),
              ),
              TextField(
                controller: txtjumlah,
                decoration: InputDecoration(hintText: 'Jumlah'),
              ),
              TextField(
                controller: txtpenerbit,
                decoration: InputDecoration(hintText: 'Penerbit'),
              ),
               TextField(
                controller: txtthnterbit,
                decoration: InputDecoration(hintText: 'thnterbit'),
              ),
              Divider(height: 5.0),
              ElevatedButton(child: Text("Tambah"), onPressed: onTambah),
            ],
          ),
        ),
        new Column(
          children: data,
        )
      ],
    );
  }
}
