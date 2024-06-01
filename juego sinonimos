package application;

import java.util.Arrays;
import java.util.HashMap;
import java.util.Map;
import java.util.Random;

import javafx.application.Application;
import javafx.geometry.Insets;
import javafx.geometry.Pos;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.control.Label;
import javafx.scene.control.TextField;
import javafx.scene.layout.VBox;
import javafx.scene.paint.Color;
import javafx.scene.text.Font;
import javafx.scene.text.FontWeight;
import javafx.scene.text.TextAlignment;
import javafx.stage.Stage;

public class Batalla_de_Palabras_Sinonimos_y_Antonimos_en_Accion extends Application {

    private Stage primaryStage;
    private String palabraActual;
    private TextField tfRespuesta = new TextField();
    private boolean esSinonimo;
	private Label lblResultado;
	private Map<String, String[]> sinonimos = new HashMap<>();
    private Map<String, String[]> antonimos = new HashMap<>();
	private Stage instruccionesStage;
	public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage stage) {
        primaryStage = stage;
        mostrarBienvenida();
    }

    private void mostrarBienvenida() {
        primaryStage.setTitle("Batalla de Palabras Sinonimos y Antonimos en Accion");

        Label txtBienvenida = new Label("Hola, Bienvenido al juego\nBatalla de Palabras: Sinónimos y Antónimos en Acción");
        txtBienvenida.setFont(Font.font("Bradley Hand ITC", FontWeight.BOLD, 30));
        txtBienvenida.setTextFill(Color.GREEN);
        txtBienvenida.setTextAlignment(TextAlignment.CENTER);

        Label fraseEspero = new Label("ESPERO QUE LO DISFRUTES");
        fraseEspero.setFont(Font.font("Bradley Hand ITC", FontWeight.BOLD, 32));
        fraseEspero.setTextFill(Color.RED);

        Button btnSiguiente = new Button("Siguiente");
        btnSiguiente.setOnAction(e -> mostrarInstrucciones());
        primaryStage.close(); // Cerramos la ventana de instrucciones
        
        primaryStage.close();

        VBox vboxBienvenida = new VBox(txtBienvenida, fraseEspero, btnSiguiente);
        vboxBienvenida.setAlignment(Pos.CENTER);
        vboxBienvenida.setSpacing(20);

        Scene sceneBienvenida = new Scene(vboxBienvenida, 750, 250);
        primaryStage.close();
        primaryStage.setScene(sceneBienvenida);
        
        primaryStage.show();
        
        
    }

    private void mostrarInstrucciones() {
        instruccionesStage = new Stage();
        instruccionesStage.setTitle("Instrucciones de Juego");

        Label lblInstrucciones = new Label("INSTRUCCIONES DE JUEGO");
        lblInstrucciones.setFont(Font.font("Bradley Hand ITC", FontWeight.BOLD, 40));
        lblInstrucciones.setTextFill(Color.ORANGE);

        Label textoResto = new Label("1). Las palabras deben ser escritas en minúsculas.\n" +
                "2). Debes tener una correcta ortografía y hacer uso de las tildes.\n" +
                "3). No puedes usar ayuda externa (familiar, celular, etc).");
        Label fraseEspero = new Label("ESPERO QUE LO DISFRUTES");
        fraseEspero.setFont(Font.font("Bradley Hand ITC", FontWeight.BOLD, 32));
        fraseEspero.setTextFill(Color.RED);
        
               
        
        textoResto.setTextFill(Color.BLACK);
        textoResto.setFont(Font.font("Bradley Hand ITC", FontWeight.BOLD, 26));

        VBox vboxInstrucciones = new VBox(lblInstrucciones, textoResto);
        vboxInstrucciones.setAlignment(Pos.CENTER);
        vboxInstrucciones.setSpacing(20);
        vboxInstrucciones.setPadding(new Insets(20));
        
        

        Button btnComenzar = new Button("Iniciar juego"); // Agregamos el botón "Iniciar juego"
        instruccionesStage.close(); // Cerramos la ventana de instrucciones
        btnComenzar.setOnAction(e -> iniciarJuego());
        
        
 

        
        vboxInstrucciones.getChildren().add(btnComenzar); // Agregamos el botón al VBox

        Scene sceneInstrucciones = new Scene(vboxInstrucciones, 750, 280);
        primaryStage.setScene(sceneInstrucciones);
        primaryStage.show();
    }


    private void iniciarJuego() {
        // Aquí puedes cambiar el tamaño y el color de la fuente
        Label lblPalabra = new Label();
        lblPalabra.setFont(Font.font("Bradley Hand ITC", FontWeight.BOLD, 20)); // Cambia el tamaño y el estilo de la fuente aquí
        lblPalabra.setTextFill(Color.BLACK); // Cambia el color de la fuente aquí

        lblResultado = new Label(); // Inicializamos el nuevo label
        lblResultado.setFont(Font.font("Bradley Hand ITC", FontWeight.BOLD, 20));
        lblResultado.setTextFill(Color.BLACK);

        Button btnVerificar = new Button("Verificar respuesta");
        btnVerificar.setOnAction(e -> verificarRespuesta(lblPalabra));

        VBox vbox = new VBox(lblPalabra, tfRespuesta, btnVerificar, lblResultado); // Agregamos lblResultado al layout
        vbox.setAlignment(Pos.CENTER);
        vbox.setSpacing(20);

        Scene scene = new Scene(vbox, 700, 250);
        primaryStage.setScene(scene);
        primaryStage.show();
        
        sinonimos.put("rápido", new String[]{"veloz", "ligero", "ágil", "expedito", "pronto", "acelerado", "presto", "raudo", "celerado", "vivo"});
        sinonimos.put("grande", new String[]{"enorme", "gigante", "amplio", "extenso", "vasto", "colosal", "inmenso", "mayúsculo", "monumental", "descomunal"});
        sinonimos.put("feliz", new String[]{"contento", "alegre", "satisfecho", "gozoso", "jubiloso", "regocijado", "radiante", "feliz", "optimista", "satisfecho"});
        sinonimos.put("amor", new String[]{"cariño", "afecto", "devoción", "pasión", "adoración", "querencia", "apego", "amistad", "ternura", "simpatía"});
        sinonimos.put("guapo", new String[]{"atractivo", "bello", "bonito", "hermoso", "apuesto", "galán", "elegante", "encantador", "bien parecido", "esbelto"});
        sinonimos.put("inteligente", new String[]{"brillante", "perspicaz", "astuto", "ingenioso", "sagaz", "lúcido", "listo", "sabio", "culto", "erudito"});
        sinonimos.put("rico", new String[]{"adinerado", "opulento", "afortunado", "próspero", "abundante", "millonario", "adinerado", "opulento", "próspero", "abundante"});
        sinonimos.put("claro", new String[]{"luminoso", "nítido", "transparente", "diáfano", "evidente", "manifiesto", "patente", "visible", "notorio", "explícito"});
        sinonimos.put("fácil", new String[]{"sencillo", "simple", "manejable", "cómodo", "práctico", "elemental", "asequible", "comprensible", "entendible", "accesible"});
        sinonimos.put("nuevo", new String[]{"reciente", "moderno", "actual", "fresco", "inédito", "novedoso", "original", "juvenil", "renovado", "recién llegado"});

        antonimos.put("rápido", new String[]{"lento", "tardío", "perezoso", "moroso", "postergador", "pausado", "calmado", "tranquilo", "plácido", "sereno"});
        antonimos.put("grande", new String[]{"pequeño", "diminuto", "chico", "minúsculo", "reducido", "insignificante", "ínfimo", "pequeñito", "microscópico", "nanométrico"});
        antonimos.put("feliz", new String[]{"triste", "desdichado", "infeliz", "melancólico", "deprimido", "desgraciado", "desventurado", "desolado", "afligido", "miserable"});
        antonimos.put("amor", new String[]{"odio", "desprecio", "antipatía", "repulsión", "aversión", "enemistad", "rencor", "resentimiento", "animadversión", "desafecto"});
        antonimos.put("guapo", new String[]{"feo", "desagradable", "horrible", "repulsivo", "grotesco", "desproporcionado", "desaliñado", "desarreglado", "desastrado", "deslucido"});
        antonimos.put("inteligente", new String[]{"tonto", "bruto", "idiota", "estúpido", "imbécil", "necio", "ignorante", "inexperto", "incauto", "ingenuo"});
        antonimos.put("rico", new String[]{"pobre", "indigente", "mendigo", "necesitado", "desposeído", "desfavorecido", "desprotegido", "desvalido", "desamparado", "desasistido"});
        antonimos.put("claro", new String[]{"oscuro", "turbio", "opaco", "sombreado", "ambiguo", "confuso", "difuso", "nebuloso", "vago", "incomprensible"});
        antonimos.put("fácil", new String[]{"difícil", "complicado", "duro", "complejo", "intrincado", "enrevesado", "laberíntico", "complicado", "arduo", "espinoso"});
        antonimos.put("nuevo", new String[]{"viejo", "antiguo", "usado", "gastado", "obsoleto", "desgastado", "vetusto", "añejo", "antiquísimo", "rancio"});

        generarPalabra(lblPalabra);
    }

    private void generarPalabra(Label lblPalabra) {
        Random rand = new Random();
        if (!sinonimos.isEmpty()) {
            palabraActual = (String) sinonimos.keySet().toArray()[rand.nextInt(sinonimos.size())];
            esSinonimo = rand.nextBoolean();
            if (esSinonimo) {
                lblPalabra.setText("¿Cuál es un sinónimo de '" + palabraActual + "'?");
                lblPalabra.setTextFill(Color.BLUE); // Cambia el color de la fuente aquí
            } else {
                lblPalabra.setText("¿Cuál es un antónimo de '" + palabraActual + "'?");
                lblPalabra.setTextFill(Color.RED); // Cambia el color de la fuente aquí
            }
            lblPalabra.setFont(Font.font("Calibry", FontWeight.BOLD, 20)); // Cambia el estilo a negrita
        }
    }

    private void verificarRespuesta(Label lblPalabra) {
        String respuesta = tfRespuesta.getText();
        if ((esSinonimo && Arrays.asList(sinonimos.get(palabraActual)).contains(respuesta)) ||
            (!esSinonimo && Arrays.asList(antonimos.get(palabraActual)).contains(respuesta))) {
            lblResultado.setText("Respuesta correcta\n¡Excelente trabajo!");
            lblResultado.setTextFill(Color.GREEN);
            lblResultado.setFont(Font.font("Calibry", FontWeight.BOLD, 26)); // Cambia el tamaño y el estilo de fuente aquí
            if (!sinonimos.isEmpty() && !antonimos.isEmpty()) {
                generarPalabra(lblPalabra);
            }
        } else {
            lblResultado.setText("Respuesta incorrecta\n¡Sigue intentando!");
            lblResultado.setTextFill(Color.PURPLE);
            lblResultado.setFont(Font.font("Ravie", FontWeight.BOLD, 26)); // Cambia el tamaño y el estilo de fuente aquí
            if (esSinonimo) {
                lblPalabra.setText("¿Cuál es un sinónimo de '" + palabraActual + "'?");
                lblPalabra.setTextFill(Color.BLUE);
                lblPalabra.setFont(Font.font("Ravie", FontWeight.BOLD, 20));
            } else {
                lblPalabra.setText("¿Cuál es un antónimo de '" + palabraActual + "'?");
                lblPalabra.setTextFill(Color.RED);
                lblPalabra.setFont(Font.font("Ravie", FontWeight.BOLD, 20));
            }
        }
        tfRespuesta.clear();
    }

}
