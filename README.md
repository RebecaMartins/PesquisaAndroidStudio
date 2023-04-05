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






Referências:
https://developer.android.com/reference/android/widget/TextView
