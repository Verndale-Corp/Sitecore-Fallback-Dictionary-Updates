Verndale Sitecore Dictionary and Language Fallback

Purpose
Update the Sitecore Dictionary logic to take language fallback into account.

Compatibility
The codebase is compatible with Sitecore 6.6.x releases and at least through Sitecore 7.2.x.
This assumes you are using the latest version of the Partial Language Fallback Module
http://marketplace.sitecore.net/en/Modules/Language_Fallback.aspx

How to build code and deploy the solution
1. When using the fallback module, make sure to compile the source code to get the dll, do not use the one within the package.

2. Download and unzip the Verndale.SharedSource.zip from this repository, it contains a class library
3. The important file in this is TryGetFromFallbackLanguage.cs

4. Download the App_Config folder, there are necessary updates within Sitecore.SharedSource.PartialLanguageFallback.config.example
You can use the whole thing or take the parts from it that you need and add to your fallback.config
It contains an additional class to be used in the getTranslation pipeline

Testing
1. Set the dictionaryDomain in the fallback.config site node for your site to site specific dictionary domain item guid
2. Add a dictionary entry in the fallback language and add a language version for a language that is falling back
3. Update code to use the Translate method to output the dictionary phrase
4. Change the site context language to the falling back language and make sure the phrase it being pulled
5. make sure that enableFallback is true for this site and that the enable Fallback checkbox is checked on the Dictionary Entry template fields

Review the blog series about Partial Language Fallback on Sitecore, http://www.sitecore.net/en-gb/Learn/Blogs/Technical-Blogs/Elizabeth-Spranzani.aspx
