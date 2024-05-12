**Intro**: Netflix is a global streaming giant, known for its vast library of movies, TV shows, and original content, catering to millions of subscribers worldwide with its diverse entertainment offerings and user-friendly platform. With a disruptive business model and a commitment to innovation, Netflix has transformed the way audiences consume and experience entertainment in the digital age.

This dashboard provides an in-depth exploration of Netflix's vast library of content, spanning various genres and years. From subscriber demographics and viewing trends to content analysis and runtime distribution, this analysis offers valuable insights into Netflix's diverse offerings and audience engagement.

**Dashboard**:

![image](https://github.com/Shibbu91/Bi-Projects/assets/87035922/bc1032ff-b68a-4f31-a8e6-8efd5c81598c)

**DAX Queries**:

Avg IMBD = AVERAGE(titles[imdb_score])

Movies = CALCULATE(COUNTA(titles[type]) , FILTER(titles, titles[type] = "MOVIE" ))

Runtime hours = INT(SUM(titles[runtime])/60)

Total content = COUNT(credits[id])

TV Shows = CALCULATE(COUNT(titles[type]) , FILTER(titles, titles[type] = "SHOW"))

