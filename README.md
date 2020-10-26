# 
/*public class TextingMetodoMatrices {

    
    public static void main(String[] args) {
        // TODO code application logic here
        
       ClaseArreglos manejador = new ClaseArreglos(); 
       
        Scanner sc = new Scanner(System.in);
        //creacion del arreglo con datos desordenados
    int [] arreglo2 = {45, 53, 85, 13, 95, 16, 5, 26, 99,10};
    //Cracion de variables tipo numericas
   int posicion, busqueda;
        //Frace inicial que se muestra en pantalla
   System.out.println("Arreglo en desorden: ");
        System.out.println("               ");
        //Arreglo que el usuario podra ver de forma desordenada
        System.out.println(Arrays.toString(arreglo2)); 
        
        System.out.println("Digite un elementos del arreglo: ");
        System.out.println("               ");
        //Pedido de scanner para que el usuario pueda ingresar datos en la variable busqueda 
        busqueda = sc.nextInt();
        
        System.out.println("                  ");
   //Uso de erramienta tipo arreglo que nos permite ordenar los datos del arreglo de menor a mayor
   Arrays.sort(arreglo2);
   System.out.println("            ");
        System.out.println("Arreglo ordenado: ");
        System.out.println("                 ");
        
   //arreglo que el usuario podra ver de forma ordenada
     System.out.println("                 ");
        System.out.println(Arrays.toString(arreglo2));
          System.out.println("                 ");
        
        posicion = Arrays.binarySearch(arreglo2,busqueda);
   //impresion en pantalla de resultado de la busqueda
        System.out.println("El elemento buscado esta en la posicion: "+ posicion);   
     
    }
    
}
*/



/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package textingmetodomatrices;

import java.util.Arrays;
import java.util.Scanner;

/**
 *
 * @author Samuel
 */
public class ClaseArreglos {
    
    private int tamaño;
     
    public int [] shellSort(){
        int [] arregloo = new int[tamaño];
     int salto, aux, i;
        boolean cambios;
  
        for (salto = arregloo.length / 2; salto != 0; salto /= 2) {
            cambios = true;
            while (cambios) {   // Mientras se intercambie algún elemento                                         
                cambios = false;
                for (i = salto; i < arregloo.length; i++)   // se da una pasada
                {
                    if (arregloo[i - salto] >arregloo[i]) {       // y si están desordenados
                        aux = arregloo[i];                  // se reordenan
                        arregloo[i] = arregloo[i - salto];
                        arregloo[i - salto] = aux;
                        cambios = true;              // y se marca como cambio.                                   
                    }
                }
            }
        }
        return arregloo;
       
    }
    
    
     public  int []insercion() { 
         //uso de arreglo tipo int, que puede ser modificado al gusto
        int [] arreglooo = new int[tamaño];
	
        //uso de objeto tipo int que almacenara todo el arreglo
         int n = arreglooo.length;  
	 
         //inicio del ciclo for que recorrera el arreglo
        for (int j = 1; j < n; j++) {  
	
            //almacenamiento de el arreglo recorrido dentro de un objeto tipo int
            int key = arreglooo[j];  
	    
            //almacenamiento del recorrido del arreglo -1 en un objeto tipo int 
            int i = j-1;  
	    
            //uso de ciclo while para verificar parametros dentro del arreglo
            while ( (i > -1) && ( arreglooo [i] > key ) ) {  
                arreglooo [i+1] = arreglooo [i];  
                i--;  
            }  
            arreglooo[i+1] = key;  
        }
        
        return arreglooo;
     }
     
     
     public  String []eliminarDatosRepetidos() {  
         //arreglo con datos predeterminados que puede ser modificado al gusto
        String [] datos = {"c","4","1","2","marina","6","7","2","2","5","5","6","2","4","2","9","a","a","b","vannesa","marina","vannesa"};
        
        //inicio del ciclo for para el recorrido del arreglo
       for(int a=0;a<datos.length;a++){
       
             //inicio del segundo siclo para recorrido de del arreglo -1
			for(int b=0;b<datos.length-1;b++){
			
           //si a es diferente a b se inicia lo sigiente
				if(a!=b){
				
                             //si no se encontro dato repetido dentro de dato este prosige sin problemas
					if(!(datos[a] == null ? datos[b] == null : datos[a].equals(datos[b])))
                                        {
					} 
                                        else 
                                        {
					
                                            //si encuentra algun dato repetido, eliminamos datos repetidos
                                            
                                            datos[a]="";
                                        }

				        }
			    }
		}

		// mostrar valores solo una  vez

		int n=datos.length;

		for (int i=0;i<=n-1;i++){

			if(!"".equals(datos[i])){

				System.out.println( datos[i ]);
			}
		}
                  return datos;
     }
     
     
       public  int []elementoMayor(int [] arregloa) {  
       //inicio de Scanner para pedido de datos por el usuario
        Scanner teclado = new Scanner(System.in);
	
       //frace que pide el el tamaño del arreglo y el arreglo en la parte porterior
        System.out.print("Por favor ingrese el tamaño del array: ");
        int n = teclado.nextInt();
        int arreglo1 [] = new int [n];
	
        //inicio de ciclo de recorrido del arreglo y llenado del arreglo
        for (int i = 0; i < arreglo1.length; i++) {
           System.out.print("Ingrese dato "+(i+1)+": ");
            arreglo1 [i] = teclado.nextInt();
        }
	
       //uso de objetos tipo int
        int mayor, menor;
	
        //comparacion de objetos con arreglo en la posicion 0
        mayor = menor = arreglo1 [0];
	
       //inicio de ciclo de recorrido del arreglo
        for (int i = 0; i < arreglo1.length; i++) {
	
            //si el arreglo se encuentra en una posicion mayor dentro del arreglo, este se almacenara en mayor
            if(arreglo1 [i] > mayor) {
                mayor = arreglo1[i];
            }
	    
            //pero si este se encuentra en la parte menor, este se almacenara en menor 
            if(arreglo1[i]<menor) {
                menor = arreglo1[i];
            }
        }
	
        System.out.println("El mayor valor es: "+mayor);
        System.out.println("El menor valor es: "+menor);
        
        return arreglo1;
     }
       
       public  int []busquedaBinaria() {  
        Scanner sc = new Scanner(System.in);
        //creacion del arreglo con datos desordenados
    int [] arreglo2 = null ;
    
    //Cracion de variables tipo numericas
   int posicion, busqueda;
           
        //Pedido de scanner para que el usuario pueda ingresar datos en la variable busqueda 
        busqueda = sc.nextInt();
	
      //cracion de la variable i con un valor de 0
        int i=0;
	
        //inicio de bucle while que compruebe la existencia del dato dentro del arreglo
      while(arreglo2[i]== busqueda){
                i++;    
  
   //Codigo con el cual posicion podra obtener la busqueda binaria con el arreglo ordenado y el dato dado por el usuario con una herramienta de arreglo
   posicion = Arrays.binarySearch(arreglo2,busqueda);
 
       
        }
        return arreglo2; 
       }
       
       
        public  int []moda() {  
            //inicio de arreglo tipo int el cual puede ser modificado al gusto
        int [] arreglo3 = new int[tamaño];
	
        //inicio de objetos tipo int con un valor de 0
        int maximaVecesQueSeRepite = 0;
         int moda = 0;

//inicio de recorrido de arreglo con i
for(int i=0; i<arreglo3.length; i++){

    //inicio de objeto tipo int con valor de 0
int vecesQueSeRepite = 0;

//inicio de recorrido de arreglo con j
for(int j=0; j<arreglo3.length; j++){

    //si el dato i dentro del arreglo es exactamente igual al dato j dentro del arreglo, este maracara las veces que se repite aumentando en 1
if(arreglo3[i] == arreglo3[j])
vecesQueSeRepite++;
}

//si las vecesQueSeRepite es mayor a maximaVecesQueSeRepite el arreglo i se almacenara en moda
if(vecesQueSeRepite > maximaVecesQueSeRepite){
moda = arreglo3[i];

//y el valor de maximaVecesQueSeRepite sera vecesQueSeRepite
maximaVecesQueSeRepite = vecesQueSeRepite;
}
}
        return arreglo3; 
       }
        
	
        public int[][] sumaMatrices(int[][] m1, int[][] m2)
        {
            //inicio de objetos tipo inte con el valor de ambas matrices
            int a=m1.length;
            int b=m2.length;
	    
            //inicio de matriz m3 la cual almacenara a los objetos a y b
            int[][] m3= new int[a][b];
	    
            //si toda la matriz m1 y m2 es diferente a la matriz m1[0] y m2[0] marcara un error ya que no son simetricas
            if(m1.length != m2.length || m1[0].length != m2[0].length)
            {
                System.out.println("Error, las matrices no son cuadradas");
                System.exit(0);
            }
	    
            //pero si ni es asi iniciara un ciclo que recorrera ambas matrices
            else
                for(int i=0; i<a; i++)
                {
                   for(int x=0; x < b; x++)
                    {
		    
                        //el resultado de la suma de m3 sera m1+m2
                        m3[i][x] = m1[i][x] + m2[i][x];
                
                    }
                }
            return m3;
        }
        
	
         public double[][] inversa(double [][]B,double [][]C ){
         Scanner entrada=new Scanner(System.in);
        double determinante,a,b,c,d,e,f,g,h,x;

        System.out.println("Ingrese los valores de la matriz  :");
        for(int i=0;i<3;i++){
            for(int j=0;j<3;j++){
                B[i][j]=entrada.nextByte();
            }
        }
        System.out.println();
        for(int i=0;i<3;i++){
            for(int j=0;j<3;j++){
                System.out.print("|"+ B[i][j] +"|");
            }
            System.out.println();
        }
        determinante=(B[0][0]*((B[1][1]*B[2][2])-(B[1][2]*B[2][1])))-(B[0][1]*((B[1][0]*B[2][2])-(B[2][0]*B[1][2])))+(
                B[0][2]*((B[1][0]*B[2][1])-(B[2][0]*B[1][1])));
        System.out.println();
        System.out.println("Determinate:" + determinante);
        System.out.println();

        if(determinante!=0){
            a=((B[1][1]* B[2][2] - B[2][1]* B[1][2]))/determinante;
            b=(-(B[1][0]* B[2][2] - B[2][0]* B[1][2]))/determinante;
            c=((B[1][0]* B[2][1] - B[2][0]* B[1][1]))/determinante;
            d=(-(B[0][1]* B[2][2] - B[2][1]* B[0][2]))/determinante;
            e=((B[0][0]* B[2][2] - B[2][0]* B[0][2]))/determinante;
            f=(-(B[0][0]* B[2][1] - B[2][0]* B[0][1]))/determinante;
            g=((B[0][1]* B[1][2] - B[1][1]* B[0][2]))/determinante;
            h=(-(B[0][0]* B[1][2] - B[1][0]* B[0][2]))/determinante;
            x=((B[0][0]* B[1][1] - B[1][0]* B[0][1] ))/determinante;

            C[0][0]=a;
            C[0][1]=d;
            C[1][0]=b;
            C[1][1]=e;
            C[1][2]=h;
            C[2][0]=c;
            C[2][1]=f;
            C[2][2]=x;
            C[0][2]=g;
               System.out.println("Inversa: ");
            for(int i=0;i<3;i++){
                for(int j=0;j<3;j++){
                    
                    System.out.print("|"+ C[i][j] +"|");
                  
                }
               
                System.out.println();
            } 
        }
        else{
            System.out.print("La matriz no tiene inversa          ");
        }
        return C;
         }
         
	 
         public int[][] tranpuesta(int [][] m ){
            //mensaje enviado al usuario 
        System.out.println("matriz origunal: ");
	
        //inicio de cicos que recorreran toda la matriz
  for (int i = 0; i < m.length; i++) {
   for (int j = 0; j < m[0].length; j++) {
   
    //impresion de la matriz
    System.out.print("          "+m[i][j]);
    
   }
   
   System.out.println();

  }
  
  //mensaje enviado al usuario 
  System.out.println("matriz transpuesta: ");
  
  //inicio de cicos que recorreran toda la matriz
  for (int i = 0; i < m.length; i++) {
  
   for (int j = 0; j < m.length; j++) {
    //impresion de matriz transpuesta
    
    System.out.print("          "+m[j][i]);

   }
   
   System.out.println();
 
  }

  return m;
  
    }
        
	
         public int[][] multiplacionMatrices(int[][] m1, int[][] m2)
        {
            int a=m1.length;
            int b=m2.length;
            int[][] matriz3= new int[a][b];
            
            if(m1.length != m2[0].length && m1[0].length != m2.length)
        {
            System.out.println("Error, las matrices no son cuadradas");
                System.exit(0);
        }
            else
                
             for (int x= 0; x<matriz3.length; x++)
          for (int y=0; y<matriz3[0].length; y++)
              for (int z=0; z<m2.length; z++)
                  matriz3[x][y] = matriz3[x][y] + m1[x][z] * m2[z][y];
            
            return matriz3;
        }
  
  
         public int[][] matrizEspiral(int n1, int n2){
	 
	 //inicio de Scanner para el uso del usuario
    Scanner sc;
    sc=new Scanner(System.in);
    
    //inicio de la matriz con valores nulos
    int[][] matriz = null;
    
    // si la matriz n1 y n2 so diferentes mandara un mensaje al usuario marcando un error ya que se necesita una matriz simetrica para el uso de este
    if(n1 != n2)
    {
        System.out.println("Falla, las matriz no es cuadrada");
        System.exit(0);
    }
    
    //si este si es simetrica se iniciara el llenado de la matriz
    else{
    
    matriz = new int[n1][n2];
    int a=0;
    int b=n1-1;
    int valor=0;
    //inicio de ciclo
    for(int j=0; j<matriz.length; j++){
    
    //llenar la fila superior
     System.out.println("Ingresa los datos que almacenara la fila superior");
    for(int i = a; i<=b; i++){
        matriz[a][i] =sc.nextInt() ;
    }System.out.println("");
    
    //llenar la columna extremo superior
        System.out.println("Ingresa los valores que almacenara la columna del extremo superior");
    for(int i = a+1; i<=b; i++){
        matriz[i][b] = sc.nextInt() ;
    }System.out.println("");
    
    //llenar la fila inferior de derecha a izquierda
        System.out.println("Ingresa los valores que almacenara la fila inferior de derecha a izquierda");
    for(int i = b-1 ;i>=a; i--){
        matriz[b][i] = sc.nextInt();
    }System.out.println("");
    
    //llenar la columna del extremo izquierdo de abajo hacia arriba
        System.out.println("Ingresa los valores que almacenara la columna del extremo izquierdo de bajo hacia arriba");
    for(int i = b-1 ;i>=a+1; i--){
        matriz[i][a] = sc.nextInt();
    }System.out.println("");
    
    a++;
    b--;
    }
    }
    return matriz;
}
         
	 
         public Integer [][] matrizSimetrica(int [][] matriz1){
	 
             //inicio de Scanner para el uso del usuario
             Scanner dato=new Scanner(System.in);
	     
             //Inicio de obejtos con valores de 0 unulo
              Integer tam=0;
       boolean teste=false;
       
     //Mensaje enviado al usuario junto al uso de scanner el cual dara el tamaño de la matriz
       System.out.println("ingrese el tamaño de la matriz");
       tam=dato.nextInt();
       Integer mat[][]=new Integer[tam][tam];
       
     //Mensaje enviado al usuario
        System.out.println("ingrese los elementos de la matriz");
	
        //inicio de ciclos for que junto a otro mesaje al usuario y uso de scanner para el llenado de la matriz 
        for (int i=0;i<tam;i++){
            for (int j=0;j<tam;j++){
                System.out.println("columna"+(i+1)+"  fila"+(j+1));
                mat[i][j]=dato.nextInt();
            }
        }
	
     //uso de ciclo para recorrer la matriz y si esta es cimetrica el programa la marcara como simetrica y el programa terminara
        for (int i= 0; i <tam; i++){
   for (int j=0; j <tam; j++){
    if ( (mat[i][j]) == (mat[j][i])){
     teste = true;
     
    }
    
    //Pero si no es simetrica maracara como que no es simetrica y el programa terminara
    else {
     teste = false;
    }
    
   }
  }
  
  if (teste == true){
   System.out.println("la matriz es simétrica");
  }
  else {
   System.out.println("la matriz no es simétrica"); 
  }
        return mat;
 }

        
         
}
