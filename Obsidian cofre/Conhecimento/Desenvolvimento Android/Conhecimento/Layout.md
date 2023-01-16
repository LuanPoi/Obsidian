Definem a estrutura, hierarquia e parâmetros dos elementos visuais.

Essas definições de estrutura são feitas por meio das [[ViewGroup]] que são sub-classes de [[View]] e normalmente tem a terminação 'Layout' no seu nome.

É possível colocar um layout dentro do outro.

Um layout segue uma lógica de parent e child, um parent contém 1-N child e um child pertence a 1 parent.

Algumas desses layouts são:
* [[ConstraintLayout]] *\*Mais usado\**
* [[RelativeLayout]]
* [[AbsoluteLayout]]
* [[LinearLayout]]
* [[GridLayout]]

As duas formas de manipular os layouts são:
* Por meio do [[Layout Editor]].
* Direto no arquivo [[XML]].