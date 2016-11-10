# MPAA website

The MPAA application is a Jekyll generated static website, built from JSON datafiles containing the questions,
help and information content, and page/question composition and pathways.

_data/:
	
	questions.json
	pages.json
	content.json

questions.json format:

{ "Questions", [

	{
		"id": 1,
		"question": "This is the question text?",
		"answers": ["Yes", "No"]
	},
	
	...
	
	]
}

* Note: the answers need not be Yes/No, however only "Yes" answers are tracked.
		Questions with more complex answer sets can be used for navigation purposes.

pages.json format:

{ "Pages", [

	{
		"id": 1,
		"title": "Page title",
		"questions": [1, 2, 3, 4, 5],
		"next": 6
	},
	{
		"id": 6,
		"title": "Page title",
		"questions": [6],
		"nav": {
			"Land": 7,
			"Sea": 14,
			"Both": 24
		}
	},
	
	...
	
	{
		"id": 15,
		"title": "Page title",
		"questions": [27],
		"next": "final"
	}]
}

* Note: "questions" consist of an array of question id's. "next" indicates the id of the next page in the flow.
		"nav" is used where several alternative answers are provided, and each alternative must correspond to a pre-defined answer.
		When "final" is specified, the next page will be the overall summary page.

{ "Content": [
	{
		"id": 1,
		"helpTitle": "Help title",
		"helpContent": "<p>This is the help content in HTML format.</p>",
		"summary": "This is the summary content in HTML format.</p>",
		"pdf": "pdffile.pdf",
		"pdfDescription": "pdf file description"
	},
	
	...
	
	]
}

* Note: there should be one entry per question.
		Yes/No questions can contain summary content which is displayed when Yes is selected, as well as on the summary page.
		Help content is applicable to any question type.