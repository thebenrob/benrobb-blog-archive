---
id: 73
title: MySQL Optimization
date: 2007-04-09T22:14:23-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/04/09/mysql-optimization/
permalink: /2007/04/09/mysql-optimization/
dsq_thread_id:
  - "4199194432"
categories:
  - Old Stuff
---
<p>I've been doing some reading recently for a (long procrastinated) assignment at school.  I've found some official looking materials as well as a recent Digg that led to some generally accepted industry expertise.  I'll give the links in a moment, but here's the point of it all.</p>
<p><strong>Low-hanging fruit</strong><br />
Don't waste time trying to tune every query in your database.  It can't be done.  Find the ones that take all the time and tune them.  The slow queries log is a good place to start. My understanding is that you can set the parameters for the slow queries log in your my.cnf file.</p>
<blockquote><p>log_slow_queries=/var/lib/mysql/slow­queries.log<br />
long_query_time=2<br />
log_long_format</p>
</blockquote>
<p><strong>EXPLAIN</strong><br />
Once you've found the queries that are taking a long time, you can use the EXPLAIN command (or the MySQL Query Browser graphical version) to see which parts of the query are taking the longest.  It gives a lot of information about the query itself, but besides the times themselves the most useful information is related to the indexes.  You can see how many records each portion has to crunch through, which indexes are available, and which indexes are being used.  This leads to tip #3.</p>
<p><strong>Index, Index, and....oh, Index.</strong><br />
Proper indexing is probably your best friend when it comes to increasing query performance.  This has limited benefits for extremely dynamic databases with a high proportion of INSERTs and UPDATEs because the indexes will have to be rebuilt each time the table is changed, but where SELECTs are the bulk of the queries (most databases) indexing can contribute to huge increases in speed</p>
<p><strong>More Info</strong><br />
<a href="http://dev.mysql.com/doc/refman/5.0/en/optimization.html"> http://dev.mysql.com/doc/refman/5.0/en/optimization.html</a><br />
<a href="http://dev.mysql.com/doc/refman/5.0/en/explain.html"> http://dev.mysql.com/doc/refman/5.0/en/explain.html</a><br />
<a href="http://dev.mysql.com/tech-resources/presentations/presentation-oscon2000-20000719/index.html"> http://dev.mysql.com/tech-resources/presentations/presentation-oscon2000-20000719/index.html</a><br />
<a href="https://benrobb.com/wp-admin/"> http://jpipes.com/presentations/mysql_perf_tuning.pdf</a> [pdf warning]<br />
<a href="http://20bits.com/2007/04/10/10-tips-for-optimizing-mysql-queries-that-dont-suck/">http://20bits.com/2007/04/10/10-tips-for-optimizing-mysql-queries-that-dont-suck/</a><br />
<a href="http://immike.net/blog/2007/04/09/how-not-to-optimize-a-mysql-query/"> http://immike.net/blog/2007/04/09/how-not-to-optimize-a-mysql-query/</a></p>
