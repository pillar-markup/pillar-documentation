

##1\.  Configuring your output

<a name="configuring"></a>
In this section we show how to configure the export from the Pillar files\.



###1\.1\.  Configuration file

Pillar exporting mechanism can be configured using [STON](http://smalltalkhub.com/#!/~SvenVanCaekenberghe/STON), a lightweight, text\-based, human\-readable data interchange format \(similar to the popular [JSON](http://www.json.org)\.



###1\.2\.  Configuration parameters



####1\.2\.1\.  baseDirectory
<a name="sec:confParam:baseDirectory"></a>Indicate where to look for files with a non\-absolute path\.

<dl><dt>Default value
</dt><dd>The current working directory.</dd></dl>


####1\.2\.2\.  configurations
<a name="sec:confParam:configurations"></a>Each configuration can define several sub configurations, each of which inherits the properties of its parent\.

<dl><dt>Default value
</dt><dd>A dictionary of default configurations from the exporters.</dd></dl>


####1\.2\.3\.  defaultScriptLanguage
<a name="sec:confParam:defaultScriptLanguage"></a>Indicate the \(programming\) language in scripts when none is specified\.
This language is used for syntax highlighting\.

<dl><dt>Default value
</dt><dd>None</dd></dl>


####1\.2\.4\.  headingLevelOffset
<a name="sec:confParam:headingLevelOffset"></a>Indicate how to convert from the level of a Pillar heading to the level of heading in your exported document\.
For example, a `headingLevelOffset` of 3 converts a 1st level Pillar heading to an `<h3>` in HTML\.

<dl><dt>Default value
</dt><dd>`0`</dd></dl>


####1\.2\.5\.  inputFiles
<a name="sec:confParam:inputFiles"></a>List the Pillar files that must be exported\.

<dl><dt>Default value
</dt><dd>None</dd></dl>


####1\.2\.6\.  internalLinksAreAllAnchors
<a name="sec:confParam:internalLinksAreAllAnchors"></a>Indicates if, by default, all internal links \(i\.e\., with no '://' inside\) should be considered anchors \(i\.e\., links inside the current page\)\.

<dl><dt>Default value
</dt><dd>`true`</dd></dl>


####1\.2\.7\.  newLine
<a name="sec:confParam:newLine"></a>The string that separates lines in the exported document\.
This is often either LF or CR\+LF but any string is possible\.

<dl><dt>Default value
</dt><dd>Depend on the operating system.</dd></dl>


####1\.2\.8\.  outputFile
<a name="sec:confParam:outputFile"></a>Indicate in which file to export input files\. This can also be a write stream\.

<dl><dt>Default value
</dt><dd>Standard output.</dd></dl>


####1\.2\.9\.  outputType
<a name="sec:confParam:outputType"></a>Indicate the kind of output desired\.

<dl><dt>Default value
</dt><dd>None</dd></dl>


####1\.2\.10\.  scrambledEmailAddresses
<a name="sec:confParam:scrambledEmailAddresses"></a>Indicate if email addresses should appear scrambled to defeat the stupiest spammers looking for them \(the default\)\. If `false`, email addresses will appear unscrambled\.

<dl><dt>Default value
</dt><dd>`true`</dd></dl>


####1\.2\.11\.  separateOutputFiles
<a name="sec:confParam:separateOutputFiles"></a>Indicate whether each input file must be exported separately or not\.

<dl><dt>Default value
</dt><dd>`false`</dd></dl>


####1\.2\.12\.  startNumberingAtHeadingLevel
<a name="sec:confParam:startNumberingAtHeadingLevel"></a>Indicate the level of Pillar heading that is going to be numbered with top level numbers\.
E\.g\., a `startNumberingAtHeadingLevel` of value `2` indicates that Pillar heading of level 1 are not numbered\.

<dl><dt>Default value
</dt><dd>`2`</dd></dl>


####1\.2\.13\.  stopNumberingAtHeadingLevel
<a name="sec:confParam:stopNumberingAtHeadingLevel"></a>Indicate the level of Pillar heading at which Pillar stops numbering\.
E\.g\., a `stopNumberingAtHeadingLevel` of value `4` indicates that Pillar heading of level 4 and more are not numbered\.

<dl><dt>Default value
</dt><dd>Infinity (never stop numbering).</dd></dl>


####1\.2\.14\.  template
<a name="sec:confParam:template"></a>Indicate the overall structure of the exported documents\.

<dl><dt>Default value
</dt><dd>`'{{{content}}}'` \(output the document as is, without any preamble or postamble\)\.</dd></dl>


####1\.2\.15\.  title
<a name="sec:confParam:title"></a>Indicate the main title of the document\.

<dl><dt>Default value
</dt><dd>`'No title'`</dd></dl>


####1\.2\.16\.  verbose
<a name="sec:confParam:verbose"></a>Indicate whether Pillar should write a verbose log when exporting\.

<dl><dt>Default value
</dt><dd>`false`</dd></dl>

