# hopscotch

[Hopscotch][1] ist eine Framework, mit dem man Produktführungen erstellen kann. Man kann die Nutzer über eine Website führen. Dabei muss man nur angeben, welcher Text zu welchen DIV angezeigt werden soll.

Man hat die Möglichkeit Funktionen nach bestimmten Events der Tour auszuführen.

{{++ Callbacks for tour events e.g. onStart, onEnd, onShow, onNext, onPrev, onClose ++} 

	{
	  id: "myTour",
	  steps: [
	{
	  target: "firststep",
	  placement: "bottom",
	  title: "My First Step",
	  onNext: ["fillText", "searchField", "Example search query"]
	}
	  ],
	  onStart: ["selectArticle"]
	}


Die Tour wird in einer json-Datei gespeichert. Diese Datei kann natürlich auch dynamisch generiert werden.

[1]:	http://linkedin.github.io/hopscotch/