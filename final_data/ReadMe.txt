@@@@ 1. posts, topic + article dataset: 
[post_articles_topic.csv] 
--> from original all posts, filtered death post + exist articles for at least another language beside en

posts	2064
-------------
en	2064
ar	1379
zh	1527
es	1760
-------------
total	6730

@@@@ 2. About the topic: 
This part, refer [post_articles_topic.xlsx] for detail

##--- Original Topic from Topic Modeling # = 7 ---
0: Man-made Incident/disaster/riots/protests
1: Elections
2: Sports/Championship/prize
3: natural disaster
4: governments + politics except elections
5: Person
6: science and discovery
-1: others

##--- original topic, # of posts distribution ---
-1	291
0	231
1	187
2	337
3	44
4	112
5	714
6	148

##updated topic -- merge to make # of posts balance

original topic #	update topic #	
-1			6	others
0			5	Man-made Incident/disaster/riots/protest
1			3	Elections
2			4	Sports
3			1	natural disaster
4			3	governments + politics except elections
5			2	Person
6			1	science and discovery

##--- updated topic, # of posts distribution ---
1(science and discovery+natural disaster)	192
2(Person)					714
3(government, politics + election)		299
4(Sports)					337
5(Man-made Incident/disaster/riots/protest)	231
6(others)					291
----------------------------------------------------
total						2064

@@@@ 3. Effort aggregated dataset: [efforts_topic.csv]
--> each row represent an article, total of 6730 rows (articles)
--> effort aggregated for 1 month after the post/event time

---> Columns:
+ postid: unique postid
+ lang: article language
+ postyear: year of the event happend (post)
+ postdatetime: post datetime in format MM/DD/YY
+ pageid: article page id
+ article_firstedit_ever_revid: article creation first revision id
+ article_firstedit_ever_date: article creation date
+ article_firstedit_ever_timestamp: article creation timestamp
+ article_firstedit_ever_size: article creation first revision size
+ totaledits_byall: total edits by *all editors* for 1 month after the post/event time 
+ totaledits_byregistered: total edits by *only registered editors* for 1 month after the post/event time
+ unique_all_editors: unique number of *total editors (unregiter editors count based on unique ip address)* for 1 month after the post/event time
+ unique_registered_editors: unique number of *total registered editors* for 1 month after the post/event time
+ total_size_added: total size added for 1 month after the post/event time
+ sizeadded_byregistered: size added by *only registered editors* for 1 month after the post/event time

+ firstedit_revid: first revision id after post/event datetime [for use of the quality measure collection]
+ firstedit_timestamp: first revision timestamp after post/event datetime
+ endfirstday_revid: end of the first day revision id after post/event datetime [for use of the quality measure collection]
+ endfirstweek_revid: end of the first week revision id after post/event datetime [for use of the quality measure collection]
+ firstmonth_revid: end of the first month revision id after post/event datetime [for use of the quality measure collection]

+ topic: post topic
+ category: category
+ updated_topic: updated topic based on section @@@@2

@@@@ 4. quality measures dataset: [quality_topic.csv]
--> each row is an article, total of 6730 rows (article)
--> each row has revisions quality measures for 5 time point of the article: 
+ o0_{}: order 0, article creation time point
+ o1_{}: order 1, first revision after the event/post time
+ o2_{}: order 2, end of the first day revision after the event/post time 
+ o3_{}: order 3, end of the first week revision after the event/post time
+ o4_{}: order 4, end of the first month revision after the event/post time

---> Columns:
+ postid: unique postid
+ lang: article language
+ postyear: year of the event happend (post)
+ postdatetime: post datetime in format MM/DD/YY
+ pageid: article page id
+ article_creation: datetime of article creation
+ o0_timestamp: revision at order 0 time point(article creation) timestamp
+ o0_size: revision at order 0 time point(article creation), size of the revision
+ o0_external_links: revision at order 0 time point(article creation), #of external links
+ o0_wiki_links: revision at order 0 time point(article creation), #of wiki links
+ o0_references: revision at order 0 time point(article creation), #of references
+ o0_section_breadth: revision at order 0 time point(article creation), section breath
+ o0_section_depth: revision at order 0 time point(article creation), section depth
+ o0_section_num: revision at order 0 time point(article creation), # of sections
+ [o1_timestamp, o1_size, o1_external_links, o1_wiki_links, o1_references, o1_section_breadth, o1_section_depth, o1_section_num]
+ [o2_timestamp, o2_size, o2_external_links, o2_wiki_links, o2_references, o2_section_breadth, o2_section_depth, o2_section_num]
+ [o3_timestamp, o3_size, o3_external_links, o3_wiki_links, o3_references, o3_section_breadth, o3_section_depth, o3_section_num]
+ [o4_timestamp, o4_size, o4_external_links, o4_wiki_links, o4_references, o4_section_breadth, o4_section_depth, o4_section_num]
+ updated_topic: updated topics, refer section @@@@2

@@@@ 5. raw revision dataset: [revision_raw_data.csv]
--> revision history for the one month after the event/post time
--> each row is a revision for all the articles





