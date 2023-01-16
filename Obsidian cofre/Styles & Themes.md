Tanto os estilos quanto os temas se resumem a pares de chave e valor dentro de um arquivo .xml.


# Styles
`Map<view attribute, value>`

Associado com e aplicado a uma única view.

Atributos de view para valores, ou seja, nos estilos a chave será um atributo que você pode usar em uma view e o valor será o recurso que você vai aplicar a este atributo.

Exemplo:
```xml
<style name="Widget.Plaid.InlineActionButton" parent="...">
	<item name="android:gravity">center_horizontal</item>
	<item name="android:textAppearance">@style/TextAppearance.CommentAuthor</item>
	<item name="android:drawablePadding">@dimen/spacing_micro</item>
</style>
```
todas as chaves poderiam sem aplicadas diretamente a view no arquivo de layout.



# Themes
`Map<theme attribute, value>`

Associado com um contexto.

Aplicado a uma hierarquia.

Sobrepõe ancestrais.

Atributos de temas para valores, ou seja, nos temas a chave tem apenas um significado semântico como por exemplo `primaryColor` ou `accentColor`, e são basicamente um dicionário de valores para serem utilizados posteriormente.

Exemplo:
```xml
<style name="Plaid" parent="...">
	<item name="colorPrimary">@color/teal_500</item>
	<item name="colorSecondary">@color/pink_200</item>
	<item name="android:windowBackground">@color/background</item>
</style>
```
as chaves tem significado apenas semantico e não referênciam atributos reais de uma view.
(a chave `android:windowBackground` é um theme attribute.)

## Theme Attributes
Apesar de parecerem com os atributos de view eles são diferentes, definir um theme attribute é como definir uma variável e seu tipo para depois ser utilizado.

### Exemplo:
Definição:
```xml
<resources>
	<attr name="colorPrimary" format="color"/>
	<attr name="actionBarSize" format="dimension"/>
</resources>
```

uso:
```xml
<style ...>
	<item name="android:background">?attr/colorPrimary</item>
</style>
```