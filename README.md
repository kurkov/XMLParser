# XMLParser
API for XML processing.
Designed with using "Finite State Machine".<br/><br/>
Here is possible usage of this API:<br/>

	parser = new XMLParser();
	
	parser.onOpenTag(new Handler {
	
		@Override
		public void handle(Tag tag) { // in tag object I want to get access
		// to name of tag, all attributes and attribute’s values
		System.out.println(tag);
		}
	})
	.onCloseTag(handler2) 
	.onTextValue(handler3) // for plain text handling (between open and close tags)
	.onStart(handler4) // will handle <?xml encoding=“utf-8”?> tag
	.onEnd(handle5) // will invoked in the end of the input file/String
	.onError(handler);
	
	parser.parse(string)
	parse.parse(file) // can be extremely big (more than jvm memory)
