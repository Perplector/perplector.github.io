---
permalink: /resume/
title: "Resume"
author_profile: false
layout: splash
---
<!--[if IE 7 ]>
<html class="ie ie7" lang="en"> <![endif]-->
<!--[if IE 8 ]>
<html class="ie ie8" lang="en"> <![endif]-->
<!--[if (gte IE 9)|!(IE)]><!-->
<html lang="en"> <!--<![endif]-->
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ site.data.cv.name }}'s CV</title>
    <meta name="author" content="{{ site.data.cv.name }}"/>
    <meta name="description" content="{{ site.data.cv.name }}'s CV"/>
    <link rel="shortcut icon" href="/favicon.png">
	<!--
    <link href="http://netdna.bootstrapcdn.com/bootstrap/3.0.2/css/bootstrap.min.css" rel="stylesheet" media="all"/>
	-->
    <link href='http://fonts.googleapis.com/css?family=Lusitana:400,700' rel='stylesheet' type='text/css'>
    <style>
        h1 {
            font-family: 'Lusitana', serif;
            font-size: 3em;
        }
		h2 {
            font-family: 'Lusitana', serif;
            font-size: 2em;
        }
		h3 {
            font-family: 'Lusitana', serif;
            font-size: 1.5em;
        }
        .skills {
            margin-right: 1em;
        }
        @media print {
            /* In case you don't want the boxes on your printout... */
            /*.label {*/
            /*border: none;*/
            /*}*/
            /* Avoid printing hrefs when this class is applied */
            .nohref a[href]:after {
                content: "";
            }
        }
    </style>
</head>
<body>
<div class="container">
    <br/>
    <div class="text-center nohref"><h1>{{ site.data.cv.name }}</h1>
        <span class="glyphicon glyphicon-envelope"></span><a href="mailto:{{ site.data.cv.email }}"> {{ site.data.cv.email }}</a>
    </div>

    <h2>Summary</h2>
    <p> {{ site.data.cv.summary.text }}</p>

    <hr/>

	<h2>Education</h2>
    {% for college in site.data.cv.education.colleges %}
    <h3><a href="{{ college.link }}"><strong>{{ college.name }}</strong></a></h3>
    <h4><em>{{ college.degree }}, {{ college.year }}</em></h4>
    {% endfor %}

    <hr/>

    <h2>Professional Experience</h2>

    {% for item in site.data.cv.professional %}
    <div class="row">
        <div class="col-xs-6 nohref"><h3><a href="{{ item.link }}"><strong>{{ item.name }}</strong></a>
        </h3>
        </div>
        <div class="col-xs-6 text-right">
            <h5><em>{{ item.start | date: "%b %Y" }} to {{ item.end | date: "%b %Y" }}</em></h5>
            <h5>{{ item.location }}</h5>
        </div>
    </div>
    <div class="row">
        <div class="col-xs-12">
            <h4><em>{{ item.title }}</em></h4>

            <p>{{ item.summary }}</p>

            <br/>
			
<!--

            <h4>Notable Projects:</h4>
            {% for project in item.projects %}
            {% if project.link %}
            <h5><a href="{{ project.link }}"><strong>{{ project.name }}</strong></a></h5>
            {% else %}
            <h5><strong>{{ project.name }}</strong></h5>
            {% endif %}

            <p>{{ project.description }}</p>

            <p> Applicable Skills:</p>

            <p>
                {% for skill in project.skills %}
                <span class="label label-default skills"> {{ skill }} </span>
                {% endfor %}
            </p>
            <br/>
            {% endfor %}
-->
        </div>
    </div>

    <br/>
    {% endfor %}

    <hr/>


	<h2>Extracurriculars</h2>

    {% for item in site.data.cv.extracurriculars %}
    <div class="row">
        <div class="col-xs-6 nohref"><h3><a href="{{ item.link }}"><strong>{{ item.name }}</strong></a>
        </h3>
        </div>
        <div class="col-xs-6 text-right">
            <h5><em>{{ item.start | date: "%b %Y" }} to {{ item.end | date: "%b %Y" }}</em></h5>
        </div>
    </div>
    <div class="row">
        <div class="col-xs-12">
            <p>{{ item.summary }}</p>

            <br/>
        </div>
    </div>

    <br/>
    {% endfor %}

    <hr/>

	<h2>Volunteering and Outreach</h2>

    {% for item in site.data.cv.volunteering %}
    <div class="row">
        <div class="col-xs-6 nohref"><h3><a href="{{ item.link }}"><strong>{{ item.name }}</strong></a>
        </h3>
        </div>
        <div class="col-xs-6 text-right">
            <h5><em>{{ item.start | date: "%b %Y" }} to {{ item.end | date: "%b %Y" }}</em></h5>
        </div>
    </div>
    <div class="row">
        <div class="col-xs-12">
            <p>{{ item.summary }}</p>

            <br/>
        </div>
    </div>

    <br/>
    {% endfor %}

    <hr/>

	<h2>Skills</h2>


    {% for skill in site.data.cv.skills %}

    <h3>{{ skill.name }}</h3>
    {% for item in skill.items %}
    <span class="label label-default skills"> {{ item.name }} </span>
    {% endfor %}
    <br/>
    {% endfor %}

    <hr/>

    <h2>Awards</h2>
    {% for item in site.data.cv.awards %}
    <h3>{{ item.name }}, <em>{{ item.year }}</em></h3>
	<h4><em>{{ item.position }}</em></h4>
    <p>{{  item.description  }}</p>
	<br/>
    {% endfor %}

    <hr/>

	<h2>Publications</h2>
	{% for item in site.data.cv.publications %}
    <div class="row">
        <div class="col-xs-6 nohref"><h3><a href="{{ item.url }}"><strong>{{ item.title }}</strong></a>
        </h3>
        </div>

		<p>
		    <b>{{ item.author }}</b>
			<br/>
            <em>{{ item.journal }}</em>
            {% if item.volume %}, vol. {{ item.volume }}{% endif %}
			{% if item.number %}, no. {{ item.number }}{% endif %}
			{% if item.pages %}, pp. {{ item.pages }}{% endif %}.
			{% if item.year %}, {{ item.year }}{% endif %}. 
            {% if item.doi %}
              <a href="http://dx.doi.org/{{ item.doi }}">
                doi: {{ item.doi }}
              </a>
            {% endif %}
        </p>

    </div>

    <br/>
    {% endfor %}

    <hr/>

</div>

</body>
</html>


