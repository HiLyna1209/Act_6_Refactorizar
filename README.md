# Act_6_Refactorizar
public class GestorInventario {

    private String nombreArticulo;
    private double precioUnitario;
    private int cantidadStock;

    public GestorInventario(String nombreArticulo,
                            double precioUnitario,
                            int cantidadStock) {
        this.nombreArticulo = nombreArticulo;
        this.precioUnitario = precioUnitario;
        this.cantidadStock = cantidadStock;
    }

    public String getNombreArticulo() {
        return nombreArticulo;
    }

    public void setNombreArticulo(String nombreArticulo) {
        this.nombreArticulo = nombreArticulo;
    }

    public double getPrecioUnitario() {
        return precioUnitario;
    }

    public void setPrecioUnitario(double precioUnitario) {
        this.precioUnitario = precioUnitario;
    }

    public int getCantidadStock() {
        return cantidadStock;
    }

    public void setCantidadStock(int cantidadStock) {
        this.cantidadStock = cantidadStock;
    }

    public void procesarActualizacion(String nombre,
                                      double precio,
                                      int cantidadNueva) {
        this.nombreArticulo = nombre;
        this.precioUnitario = precio;
        this.cantidadStock = cantidadNueva;
    }

    public double calcularTotalInventario(double descuento) {
        double subtotal = cantidadStock * precioUnitario;
        return subtotal - (subtotal * (descuento / 100.0));
    }

    public static void main(String[] args) {

        GestorInventario item =
                new GestorInventario("Laptop Pro", 12500.0, 8);

        item.procesarActualizacion(
                "Laptop Pro",
                12500.0,
                8
        );

        double totalFinal =
                item.calcularTotalInventario(10.0);

        System.out.println(
                "Artículo: " + item.getNombreArticulo()
                + " | Stock: "
                + item.getCantidadStock()
        );

        System.out.println(
                "Total inventario valorizado: $"
                + totalFinal
        );
    }
}
