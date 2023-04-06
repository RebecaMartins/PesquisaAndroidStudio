# PesquisaAndroidStudio
Pesquisa sobre algumas funções visuais do android studio, sendo elas; commons, tipos de text, buttons e widgets.


Elementos TextView: são os elementos texts visuais dentro do programa do Android Studio. São eles que definem o que vai aparecer na tela do usuário e como ele pode interagir com ela.


A seguir alguns exemplos de códigos que podem ser usados para modificar o texto mostrado na tela:

Com um layout XML - para mudar o conteúdo da exibição de texto:

<LinearLayout
      xmlns:android="http://schemas.android.com/apk/res/android"
      android:layout_width="match_parent"
      android:layout_height="match_parent">
    <TextView
        android:id="@+id/text_view_id"
        android:layout_height="wrap_content"
        android:layout_width="wrap_content"
        android:text="@string/hello" />
 </LinearLayout>

- Agora para mudar o conteúdo da visualização do texto que foi mudado na XML anterior:

 public class MainActivity extends Activity {

    protected void onCreate(Bundle savedInstanceState) {
         super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_main);
         final TextView helloTextView = (TextView) findViewById(R.id.text_view_id);
         helloTextView.setText(R.string.user_greeting);
     }
 }

Segue abaixo alguns códigos Text mostrados no próprio site:

(enum)
- TextView.BufferType > ele define as características do texto, como estático, estilizável ou editável.

(interface)
- TextView.OnEditorActionListener > definição de interface para um callback a ser invocado quando alguma ação será executada no editor.

(class)
- TextView.SavedState > estado da interface do usuário que é armazenada pelo próprio TextView para a implementação View#onSaveInstanceState.


Alguns dos muitos atributos XML:

- android:allowUndo > a opção de se desfazer tem que ser permitida para texto editável.

- android:autoLink > controla os links, como os urls e endereços de emails (que são automaticamente convertidos para links onde o usuário pode clicar e ter acesso aquele endereço).

- android:autoSizeMaxTextSize > o tamanho máximo de texto

- android:autoSizeMinTextSize > o tamanho mínimo de texto

- android:autoText > quando definido, ele se transforma em um método de entrada de texto que corrige automaticamente erros ortográficos (comuns).

-android:breakStrategy > quebra de parágrafo (o layout de quebra no texto).

- android:capitalize > quando definido, ele se transforma num método de entrada de texto e coloca automáticamente em letra maiúscula o que o usuário irá digitar a seguir.

- android:cursorVisible > torna o cursor visível (o padrão).

- android:enabled > especifica se o widget está ativado na tela.

- android:elegantTextHeight > altura elegante do texto.
 
- android:fontFamily >  família de fontes (string ou uma referência de recurso de fonte).

- android:fontVariationSettings > variações de fontes.


Bottons: Pode ser um texto ou um ícone ou ambos, ele comunica qual ação vai ocorrer quando o usuário toca-lo. Um botão pode ser criado de três maneiras dependendo do que você deseja.

Ex:
  
  <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
      xmlns:app="http://schemas.android.com/apk/res-auto"
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      android:paddingLeft="16dp"
      android:paddingRight="16dp"
      android:orientation="vertical" >
  
      <Button
          android:id="@+id/supabutton"
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:text="I'm a button" />
  
      <ImageButton
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:contentDescription="A tiny Android icon"
          android:src="@drawable/baseline_android_24"
          app:tint="#ff0000" />
  
      <Button
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:drawableStart="@drawable/baseline_android_24"
          android:drawablePadding="4dp"
          android:drawableTint="#ff0000"
          android:text="I'm a button with an icon" />
  </LinearLayout>

Ao toca-lo o botão recebe um evento de clique, para declarar o que o botão ira fazer, é preciso criar um objeto e atribuir ao botão, segue o exemplo:

findViewById<Button>(R.id.supabutton)
  .setOnClickListener {
      Log.d("BUTTONS", "User tapped the Supabutton")
  }
      
  Existem algumas opções para modificar seu botão esteticamente, ex: 
      
      Botão sem Borda
      
      <Button
  android:id="@+id/supabutton"
  style="?android:attr/borderlessButtonStyle"
  android:layout_width="wrap_content"
  android:layout_height="wrap_content"
  android:text="I'm a button" />
      
      Plano de fundo personalidzado: 
      
      <?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:drawable="@drawable/button_pressed"
          android:state_pressed="true" />
    <item android:drawable="@drawable/button_focused"
          android:state_focused="true" />
    <item android:drawable="@drawable/button_default" />
</selector>
      
Arquivo XML (Recurso desenhavel) como plano de fundo do botão:
      
      <Button
    android:id="@+id/button_send"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="@string/button_send"
    android:onClick="sendMessage"
    android:background="@drawable/button_custom"  />

 Widgets: São como vizualizações minimalistas e rapidas de dados ou funcionalidades de um app, ele é essencial na personaliação de uma tela inicial e tem diversos tipos.
      -Widgets de informação: Exibem informações importantes para o usuario como a mudança do clima, ou relógio.
      -Widgets de coleção: Apresentam variados tipos de elemntos do mesmo tipo, como coleções de um app de fotos ou artigos.
      -Widgets de controle: Exibe funções usadas com frequência para facilitar o acesso do usuário. Um exemplo disso são os widgets de apps música.
      -Widgets híbridos: São os widgets citados acima que combinam com diferentes elementos.
      
        Os unicos gestos do wigets são tocar e deslizar verticalmente, são otímos para consolidar as informações de um app. Fora isso, é possível completar o wigets com links de navegações:
      -Funções geradoras: Permite o usuários crie novos conteúdos para um app.
      -Abrir o aplicativo num nível superior em um app de informação para o usuário ter mais flexibilidade.
      É importante o tamanho ser fléxivel na tela do usuário ou facilmente redimensionado.
      
      
      
Referências:
https://developer.android.com/reference/android/widget/TextView
https://developer.android.com/guide/topics/appwidgets/overview?hl=pt-br
https://developer.android.com/develop/ui/views/components/button
      
