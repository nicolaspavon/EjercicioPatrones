# Ejercicios de DIP, ISP, SRP
## Ejercicio 1 

**DIP:** no se comple, porque la clase de mas alto nivel "analizar datos" usa responsabilidades de "BaseDeDatos", en vez de interactuar con una interfaz

**ISP:** No se cumple debido a que no hay dos clases que dependan de una misma interfaz ¯\_(ツ)_/¯

**SRP:** no se cumple, analizar datos se encarga de corroborar si cumple la condicion, lo cual puede ser responsabilidad de otra clase


## Ejercicio 2

```cs
//Insertar el código corregido

```
## Ejercicio 3 

```cs
class DataBaseObject
{
    public string Descripcion { get; }
}

public interface IBaseDeDatos{
    DataBaseObject ObtenerDato(){get;}
    void GrabarDato(string clave, DataBaseObject dato){set;}
    String[] ListarClaves(){get;}
    String[] ListarDescripcionDatos(){get;}
    DataBaseObject[] ListarDatos(){get;}
}

//Base de datos.
class BaseDeDatos : IBaseDeDatos
{
    public DataBaseObject ObtenerDato(string clave)
    {
        //Devuelve el dato correspondiente a la clave
    }
    public void GrabarDato(string clave, DataBaseObject dato)
    {
        //Graba el dato en la base de datos, bajo la clave dada
    }
    public String[] ListarClaves()
    {
        //Devuelve un String[] con todas las claves
    }
    public String[] ListarDescripcionDatos()
    {
        //Devuelve un String[] con la descripción de todas los 
        //datos almacenados en  la base
    }
    public DataBaseObject[] ListarDatos()
    {
//Devuelve un DataBaseObject[] con todos los datos almacenados en la base
    }
}
class AnlizadorDatos
{
    private IBaseDeDatos baseDatos{get; set;};
    private CumpleCondicion cumpleCondicion{get; set;};
    public void Analizar()
    {
        foreach (DataBaseObject DBObj in baseDatos.ListarDatos())
        {
            this.cumpleCondicion.CumpleCondicion(DBObj);
        }
    }

}
class Mensaje : IMensaje
{
    private void MensajeUno()
    { /*Mensaje predeterminado*/ }
    private void MensajeDos()
    { /*Mensaje predeterminado*/ }
    private void MensajeTres()
    { /*Mensaje predeterminado*/ }
}

public interface IMensaje
{
    string MensajeUno();
    string MensajeDos();
    string MensajeTres();
}

class CumpleCondicion
{
    private IMensaje mensaje = new IMensaje();
    public void Cumplecondicion(DataBaseObject DBobj)
    {
        if (DBObj == f)
            {
                mensaje.MensajeUno();
            }
        else if(DBObj == g)
            {
                mensaje.MensajeDos();
            }
        else
            {
                mensaje.MensajeTres();
            }
    }
}

```