# LOS-HOMBRES-MAS-RICOS-DEL-MUNDO-
PFont gluck;
PFont otraletra;
PFont titulo;
PImage img;
Table ricos;
void setup() {
  size(1000, 1000);
  img = loadImage("dollar.png");
  ricos=loadTable("ricos.csv", "header");
   gluck = loadFont("Calibri-LightItalic-20.vlw");
otraletra = loadFont("Calibri-Light-15.vlw");
otraletra = loadFont("Cambria-BoldItalic-40.vlw");
}
void draw() {
background(#495A49);
  for (int fila = 0; fila<ricos.getRowCount(); fila=fila+1) {
    for (int rico=300; rico<ricos.getInt(fila, 1)/100; rico=rico+3) {
      image(img, rico+50, fila*30+50);
      textFont(gluck,20);
       fill(#171717);
      text(ricos.getString(fila, 0), 20, fila*30+80);
      text(ricos.getString(fila, 4), 200, fila*30+80);
      fill(#188E17);
      textFont(otraletra,15);
      text(ricos.getString(fila,1),ricos.getInt(fila, 1)/100+100, fila*30+80);
      textFont(otraletra,40);
      text("Los Hombres Más Ricos del Mundo",200,50);
      text("En Millones De Dolares",280,650);
    }
  }
}
