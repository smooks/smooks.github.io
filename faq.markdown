### Contents

1. [What's the easiest way to get started with Smooks?](#whats-the-easiest-way-to-get-started-with-smooks)
2. [How do I use Smooks in a Maven based Project?](#how-do-i-use-smooks-in-a-maven-based-project)
3. [What "Processing Model" does Smooks employ?](#what-processing-model-does-smooks-employ)
4. [What "Configuration Model" does Smooks employ?](#what-configuration-model-does-smooks-employ)
5. [What is a "Message Fragment"?](#what-is-a-message-fragment)
6. [What is a "selector"?](#what-is-a-selector)
7. [How do I configure a Java resource?](#how-do-i-configure-a-java-resource)
8. [How do I configure an XSLT resource?](#how-do-i-configure-an-xslt-resource)
9. [How do I configure a FreeMarker resource?](#how-do-i-configure-a-freemarker-resource)
10. [How do I configure a StringTemplate resource?](#how-do-i-configure-a-stringtemplate-resource)
11. [How do I configure a Groovy resource?](#how-do-i-configure-a-groovy-resource)
12. [Is Smooks an alternative to technologies such as XSLT?](#is-smooks-an-alternative-to-technologies-such-as-xslt)
13. [Is Smooks going to be yet another Transformation Configuration Model I'll have to learn?](#is-smooks-going-to-be-yet-another-transformation-configuration-model-ill-have-to-learn)
14. [How does Smooks simplify my XSLT?](#how-does-smooks-simplify-my-xslt)
15. [XSLT supports custom Extensions (Java, Javascript etc), so can't I "mix and match" other technologies with XSLT in this way?](#xslt-supports-custom-extensions-java-javascript-etc-so-cant-i-mix-and-match-other-technologies-with-xslt-in-this-way)
16. [When would I use Smooks to apply and XSLT verses using an XSLT Processor directly?](#when-would-i-use-smooks-to-apply-and-xslt-verses-using-an-xslt-processor-directly)
17. [What sort of processing overhead is encored when using Smooks to apply XSLT?](#what-sort-of-processing-overhead-is-encored-when-using-smooks-to-apply-xslt)
18. [Can I use Java (or Groovy) to pre-process one fragment of a message and then apply an XSLT to the whole document?](#can-i-use-java-or-groovy-to-pre-process-one-fragment-of-a-message-and-then-apply-an-xslt-to-the-whole-document)
19. [Does Smooks support a Stream or SAX based processing model?](#does-smooks-support-a-stream-or-sax-based-processing-model)
20. [Can Smooks be used to process message formats other than XML?](#can-smooks-be-used-to-process-message-formats-other-than-xml)
21. [What's the difference between the Javabean Cartridge and XML Binding frameworks like JAXB, XMLBeans, XStream etc?](#whats-the-difference-between-the-javabean-cartridge-and-xml-binding-frameworks-like-jaxb-xmlbeans-xstream-etc)
22. [How do I target a resource at the document root fragment of a message without having to specify the name of the root Element?](#how-do-i-target-a-resource-at-the-document-root-fragment-of-a-message-without-having-to-specify-the-name-of-the-root-element)
23. [How do I target a resource at all Elements of a message?](#how-do-i-target-a-resource-at-all-elements-of-a-message)
24. [What happens to message elements I don't target any resources at?](#what-happens-to-message-elements-i-dont-target-any-resources-at)
25. [Can I target more than one resource at a message fragment?](#can-i-target-more-than-one-resource-at-a-message-fragment)
26. [What technologies are supported by Smooks?](#what-technologies-are-supported-by-smooks)
27. [Apart from message Transformation, what other forms of message processing are possible with Smooks?](#apart-from-message-transformation-what-other-forms-of-message-processing-are-possible-with-smooks)
28. [Can a single Smooks instance be run concurrently?](#can-a-single-smooks-instance-be-run-concurrently)
29. [Can Smooks be extended to support other transformation/processing technologies?](#can-smooks-be-extended-to-support-other-transformationprocessing-technologies)
<br/>    
<br/> 

#### **What's the easiest way to get started with Smooks?**

The easiest way to get started with Smooks is to:

1. Have a quick read of the [Smooks Basics](documentation/#basics) section.
2. Download and try out some of the [tutorials](https://github.com/smooks/smooks/tree/v1.7.1/smooks-examples).

The tutorials are the perfect base upon which to integrate Smooks into your application.


#### **How do I use Smooks in a Maven based Project?**

Take a look at [this page](maven).


#### **What "Processing Model" does Smooks employ?**

Smooks supports DOM and SAX based processing models, but adds a more "code friendly" layer on top of them. See the [user guide](documentation).


#### **What "Configuration Model" does Smooks employ?**

See the [SmooksResourceConfiguration](/javadoc/v1.7.1/smooks/org/milyn/cdr/SmooksResourceConfiguration.html) javadocs.


#### **What is a "Message Fragment"?**

See [fragment-based data processing with Smooks](documentation#fragment-based-data-processing-with-smooks).


#### **What is a "selector"?**

A Smooks transformation is specified as a series of "resource" configurations (typically made in an XML file). Smooks loads/looks-up/"selects" a resource at runtime through the resources configuration "selector" value. For an XML fragment (Element) transformation resource, the selector value is the XML Element name. When Smooks passes over the message and encounters each Element, it uses the Element's name to "select" the resources to be applied to that message fragment.

A "selector" is not always an XML Element name however. An example of this would be message parser resource configurations (CSV parser, EDI parser etc), where the selector is always "org.xml.sax.driver". [What happens when more than one parser configuration (under selector "org.xml.sax.driver") is targeted at a message e.g. where profiling is in use?](#can-i-target-more-than-one-resource-at-a-message-fragment)


#### **How do I configure a Java resource?**

Check out the [java-basic](https://github.com/smooks/smooks/tree/v1.7.1/smooks-examples/java-basic) tutorial.


#### **How do I configure an XSLT resource?**

1. Check out the [user guide](documentation#xsl-templating).
2. Check out the [tutorials](https://github.com/smooks/smooks/tree/v1.7.1/smooks-examples).


#### **How do I configure a FreeMarker resource?**

1. Check out the [user guide](documentation/#freemarker-templating).
2. Check out the templating [tutorials](https://github.com/smooks/smooks/tree/v1.7.1/smooks-examples).


#### **How do I configure a StringTemplate resource?**

1. Check out the [StringTemplateContentHandlerFactory Javadocs](/javadoc/v1.7.1/smooks/org/milyn/templating/stringtemplate/StringTemplateContentHandlerFactory).
2. Check out the templating [tutorials](https://github.com/smooks/smooks/tree/v1.7.1/smooks-examples).

#### **How do I configure a Groovy resource?**

1. Check out the [user guid](documentation/#groovy).
2. Check out the [tutorials](https://github.com/smooks/smooks/tree/v1.7.1/smooks-examples).


#### **Is Smooks an alternative to technologies such as XSLT?**

No! Smooks is a framework for performing [fragment-based data processing](documentation#fragment-based-data-processing-with-smooks) using **existing XML processing technologies** (such as XSLT).  [Read about Why Smooks was Created](documentation#why-smooks-was-created).

Other technologies supported by Smooks are: raw Java, [Groovy](https://groovy-lang.org/) script, [FreeMarker](https://freemarker.apache.org/) and [StringTemplate](https://www.stringtemplate.org/) templating.


#### **Is Smooks going to be yet another Transformation Configuration Model I'll have to learn?**

First off, don't think of Smooks as an alternative to the likes of XSLT and don't think of the Smooks configuration as a "Transformation Configuration" in the same way as an XSL Stylesheet.

The Smooks configuration should be thought of more as a "Framework Configuration" - most frameworks have a configuration of one sort or another. It's nothing like XSLT, which is basically a programming language in XML. It just defines how transformation/analysis resources are targeted at messages and message fragments. It doesn't define the low level details of each individual transformation. Also note that the Smooks configuration is quite simple in terms of the number of configuration elements you need to remember - there are only a few.

See the [SmooksResourceConfiguration](/javadoc/v1.7.1/smooks/org/milyn/cdr/SmooksResourceConfiguration) javadocs.


#### **How does Smooks simplify my XSLT?**

Smooks can be used to simplify your XSLT in a number of ways:

1. Because Smooks supports targeting of transformation resources (including XSLT) at [message fragments](documentation#fragment-based-data-processing-with-smooks), it's easier to modularize and reuse your XSLT.
2. Smooks allows you to mix and match different technologies within the context of a single message transform. This means you can transform (or pre-process) fragments of the message, not easily consumed by XSLT, using other technologies e.g. Java or Groovy. See the [xslt-groovy tutorial](https://github.com/smooks/smooks/tree/v1.7.1/smooks-examples/xslt-groovy). Unlike XSL Extensions however, it supports mixing these technologies with your XSLT, [without effecting the XSLT's portability](#xslt-supports-custom-extensions-java-javascript-etc-so-cant-i-mix-and-match-other-technologies-with-xslt-in-this-way).


#### **XSLT supports custom extensions (Java, Javascript etc), so can't I "mix and match" other technologies with XSLT in this way?**

Sure, XSLT supports custom extensions. The problem with XSLT Extensions is the effect they often have on your XSLT in terms of portability across processor implementations, as well as general stylesheet maintenance. Take a quick look at the mailing lists for some of the main XSL Processor implementations. You'll see that extension portability is a recurring topic of conversation.

Smooks helps you solve the same type of problems that XSLT Extensions are designed to solve, but by keeping the extension logic separate from the XSLT. Your stylesheets should always be vanilla XSLT, without any reference to extension code. See the [xslt-groovy tutorial](https://github.com/smooks/smooks/tree/v1.7.1/smooks-examples/xslt-groovy). It uses a Groovy Smooks resource ("extension") to pre-process a date field into XML nodes that are more consumable by XSLT, removing the convoluted date field processing logic from the XSLT, keeping the stylesheet nice and simple.


#### **When would I use Smooks to apply and XSLT verses using an XSLT Processor directly?**

1. No one transformation technology (including XSLT) is ideally suited to all transformation use cases. Some parts (fragments) of a message are going to be easily transformed via a templating approach such as XSLT (structural transformations), while others are more easily transformed using a procedural language such as Java. When you encounter situations such as this and want to avoid the type of portability issues outlined [here](#xslt-supports-custom-extensions-java-javascript-etc-so-cant-i-mix-and-match-other-technologies-with-xslt-in-this-way), Smooks offers a a nice clean solution. See the [xslt-groovy tutorial](https://github.com/smooks/smooks/tree/v1.7.1/smooks-examples/xslt-groovy). It uses a Groovy Smooks resource ("extension") to pre-process a date field into XML nodes that are more consumable by XSLT, removing the convoluted date field processing logic from the XSLT, keeping the stylesheet nice and simple.
2. Where you want to componentize your XSLTs and apply them against message fragments (verses a whole message using a single monolithic XSLT).
3. Where you have a larger message set and require a mechanism for selecting and applying the appropriate XSLT based on message profiles.


#### **What sort of processing overhead is encored when using Smooks to apply XSLT?**

We carried out some profiling in order to get an answer to this very question. The scenario we used was purposely geared in favor of XSLT. The message being processed was very flat (not hierarchical) and was not normalized and the XSLT we chose to apply was very simple. This type of scenario is especially suited to Stream/SAX based XSL processing.

What this profiling demonstrated was that in this scenario (worse case scenario) a 5% - 15% overhead is encored when comparing Smooks based application of XSLT to direct DOM based XSLT processing. However, when comparing DOM based application of XSLT (direct or via Smooks) to direct Stream/SAX based XSLT processing, we see that Stream/SAX based processing kicks ass in this type of scenario. The fact that Stream/DOM based processing can (given the right conditions) outperform DOM based processing is a long known fact.

This approach to profiling gives users of Smooks a "worse case scenario" idea of how Smooks performs when applying XSL Transforms. What users of Smooks need to remember is that Stream/SAX based processing is not well suited to all types of transforms. As well as that, Smooks offers many other features that help simplify otherwise complex transforms, while at the same time maintaining stylesheet portability across XSL Processors. We're also very keen to add Stream and SAX based processing to Smooks.

For more on the profiling we carried out, [see blog](https://jbossesb.blogspot.com/2007/03/as-you-may-already-know-jboss-esb-uses.html).

**NOTE**: Smooks v1.0 supports a SAX based processing model. More information on this to follow, or mail the User mailing list.


#### **Can I use Java (or Groovy) to pre-process one fragment of a message and then apply an XSLT to the whole document?**

Absolutely! This is a classic Smooks usecase. See the [xslt-groovy tutorial](https://github.com/smooks/smooks/tree/v1.7.1/smooks-examples/xslt-groovy). It uses a Groovy Smooks resource ("extension") to pre-process a date field into XML nodes that are more consumable by XSLT, removing the convoluted date field processing logic from the XSLT, keeping the stylesheet nice and simple. The XSLT is then applied to the "$document" (root) node.


#### **Does Smooks support a Stream or SAX based processing model?**

Smooks Core does support a SAX based processing model. Not all components have been updated to leverage the SAX processing model, but will be in time to come.

That said, we feel that people should remember that it's not as simple as "Stream/SAX based processing is faster than DOM based processing". Stream/SAX is not suited to all types of transforms. For normalized messages, the performance of Stream/SAX based processing can often suffer a lot more than an equivalent DOM based transform. Counteracting this for Stream/SAX can result in more complex and unmaintainable transformations.


#### **Can Smooks be used to process message formats other than XML?**

Absolutely! Smooks allows you configure a SAX parser on a per transform basis (based on a message profile if necessary). As long as a message is hierarchical in nature, SAX events can be generated for that message, allowing it to be consumed by Smooks. See the [edi-to-xml](https://github.com/smooks/smooks/tree/v1.7.1/smooks-examples/edi-to-xml) and [csv-to-xml](https://github.com/smooks/smooks/tree/v1.7.1/smooks-examples/csv-to-xml) tutorials.


#### **What's the difference between the [JavaBean Cartridge](documentation#java-binding) and XML Binding frameworks like JAXB, XMLBeans, XStream etc?**

The Javabeans Cartridge is not intended as a straight alternative to existing XML Binding frameworks such as those listed above. If your only requirement is that of binding XML to and from Java Objects, then you should probably go with one of the these other frameworks.

The Smooks Java binding functionality can be a very useful alternative:

1. For binding non-XML data e.g. EDI, CSV, Java (i.e. performing Java to Java transforms).
2. For binding XML data that doesn't line up with the target java object model.
3. In situations where your source data model does not conform to any schema. Some tools (e.g. JAXB and XMLBeans) require you to have an XSD, from which the Java model is generated and against which the source message is validated.
4. Performing [Expression Based Bindings](documentation#java-binding-configuration-details).
5. For creating [Virtual Object Models](documentation#java-binding-configuration-details). This can be very useful when performing model driven transformations.
6. For binding XML data where the XML model's dataset is a superset of the Java model's dataset i.e. where you need to selectively pick data from the source XML.
7. In support of complex splitting, transformation and routing (and other operations).

We're sure there are other use cases where Java binding using Smooks makes sense, but basically what we're saying is that if all you are interested in is straightforward marshalling and unmarshalling between Java and XML, then JAXB/XStream etc is probably a more straightforward option, as long as your use case fits inside the parameters set down by these frameworks. If your use case cannot be solved using JAXB (etc) without major headaches (which can often be the case), then Smooks can be an option for you!


#### **How do I target a resource at the document root fragment of a message without having to specify the name of the root Element?**

Specify the selector as "$document".


#### **How do I target a resource at all Elements of a message?**

Specify the selector as "*".


#### **What happens to message elements I don't target any resources at?**

They remain in the resulting document, untouched. This is unlike a templating type system (e.g. XSLT) where this would result in these fragments being omitted from the resulting document.


#### **Can I target more than one resource at a message fragment?**

You can. They will be sorted an applied by Smooks in order of their configuration specificity. See the [SmooksResourceConfigurationSortComparator](/javadoc/v1.7.1/smooks/org/milyn/cdr/SmooksResourceConfigurationSortComparator).


#### **What technologies are supported by Smooks?**

Smooks supports a number of technologies and [can easily be extended to support more](/javadoc/v1.7.1/smooks/org/milyn/delivery/ContentHandlerFactory). These technologies are bundled in what we call "Cartridges". A single cartridge may support more than one type of processing technology.

[See the current list of Smooks cartridges and the technologies they add support for](https://github.com/smooks/smooks/tree/v1.7.1/smooks-cartridges).


#### **Apart from message transformation, what other forms of message processing are possible with Smooks?**

In most of the Smooks documentation we talk about Smooks in the context of data transformation. However, the core of Smooks (smooks-core) knows nothing about data transformation and so does nothing specific in this area. It's basically an engine for applying "visitor" logic to data "fragments". This logic can be data transformation logic, or it can be logic for processing/analyzing data in any way you require.

So, the answer to this question is - "whatever type of processing you require". Just write the visitor implementation(s) and get Smooks to apply the logic on the target fragments. [Visitor](documentation#visitor) implementations can interact with each other via the [ExecutionContext](/javadoc/v1.7.1/smooks/org/milyn/container/ExecutionContext).


#### **Can a single [Smooks](/javadoc/v1.7.1/smooks/org/milyn/Smooks) instance be run concurrently?**

Absolutely!


#### **Can Smooks be extended to support other transformation/processing technologies?**

Sure. To add support for another transformation or processing technology, you need to implement a [ContentHandlerFactory](/javadoc/v1.7.1/smooks/org/milyn/delivery/ContentHandlerFactory) for that technology. As examples, see the following ContentHandlerFactory implementations:

1. [XslContentHandlerFactory](/javadoc/v1.7.1/smooks/org/milyn/templating/xslt/XslContentHandlerFactory): Adds support for XSLT.
2. [StringTemplateContentHandlerFactory](/javadoc/v1.7.1/smooks/org/milyn/templating/stringtemplate/StringTemplateContentHandlerFactory): Adds support for the [StringTemplate](https://www.stringtemplate.org/) templating framework.
3. [GroovyContentHandlerFactory](/javadoc/v1.7.1/smooks/org/milyn/smooks/scripting/groovy/GroovyContentHandlerFactory): Adds support for [Groovy](https://groovy-lang.org/) scripted resource.

Registering the ContentHandlerFactory is just a matter of adding a file named "content-handlers.inf" to the META-INF folder of factory's jar file and listing the implementation class(s) there in (one per line).
