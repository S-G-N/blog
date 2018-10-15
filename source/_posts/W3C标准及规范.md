---
title: W3C标准及规范
date: 2018-09-06 15:56:32
tags:
---

1. 遵循标准/兼容的意义
我们是上下游（浏览器制造商、用户）中间的接口（adapter），满足下游用户使用上游不同浏览器时看到相同的内容。在技术范围之内，使程序支持所有用户。

2.DOCTYPE（document type）
用来说明XHTML或者HTML是什么版本
过渡的(Transitional)
严格的(Strict)
框架的(Frameset)
3. namespace
<html xmlns="http://www.w3.org/1999/xhtml" lang="gb2312">
4.定义语言编码
<meta http-equiv=“Content-Type” content=“text/html; charset=gb2312” />简体中文
5.js标签
<script language="javascript" type="text/javascript">
6.css
<style type=“text/css”>

一级企业做标准，二级企业做品牌，三级企业拼销售
网页主要由三部分组成：结构（Structure）、表现（Presentation）和行为（Behavior）对应的标准也分三方面：结构化标准语言主要包括XHTML和XML，表现标准语言主要包括CSS，行为标准主要包括对象模型（如W3C DOM）、ECMAScript等。

问题：
1. 大小写
2. 属性双引号
3. 标签不闭合
4. DocType随便放

注意：
不要在注释内容中使用“--”
有标签的元素和属性的名字都必须使用小写
所有的属性必须用引号""括起来
把所有<和&特殊符号用编码表示
给所有属性赋一个值
所有的标记都必须要有一个相应的结束标记
图片添加有意义的alt属性
在form表单中增加lable，以增加用户友好度
 <label for="firstname">first name: </label>
  <input type="text" id="firstname" />




  ## W3C历史：

      




  下载LOFTER我的照片书  |
W3C是英文 World Wide Web Consortium 的缩写，中文意思是W3C理事会或万维网联盟。W3C于1994年10月在麻省理工学院计算机科学实验室成立。创建者是万维网的发明者Tim Berners-Lee。

　　W3C组织是对网络标准制定的一个非赢利组织，像HTML、XHTML、CSS、XML的标准就是由W3C来定制。W3C会员（大约500名会员）包括生产技术产品及服务的厂商、内容供应商、团体用户、研究实验室、标准制定机构和政府部门，一起协同工作，致力在万维网发展方向上达成共识。
编辑本段W3C简介:

　　自从Web诞生以来，Web的每一步发展、技术成熟和应用领域的拓展，都离不开成立于1994年10月的W3C(World Wide Web Consortium，万维网联盟)的努力。W3C是专门致力于创建Web相关技术标准并促进Web向更深、更广发展的国际组织。
　　
一、 W3C的发展历史和组织机构
　　
　　1994年10月，Web还是大学、研究机构的新宠时，Web技术和应用的发起人、被誉为Web之父的Tim Berners-Lee就敏锐地意识到Web的出路不是象牙塔中少数人的互联网络，而是供全社会使用的一种公共的信息资源和交流资源，而要达到这个目标，对其中所涉及的技术进行规范化、指导软件产业对基于此平台的技术的开发、相关技术的普及、推广和培训都必不可少。因此，Tim Berners-Lee这位Web的先驱联合CERN、DARPA和欧盟倡导并组织成立了Web的核心技术机构——W3C。
　　
　　W3C的核心最初位于Tim Berners-Lee供职的美国麻省理工学院计算机实验室(MIT/LCS)；随后，该组织迅速吸引了大量在Web上的志同道合者，开始出现多个中心的格局，随后出现的另外两个中心分别位于法国的INRIA(Institut National de Recherche en Informatique et Automatique)和日本的Keio大学(庆应大学)，其中2003年INRIA由ERCIM(Eruopean Research Consortium in Informatics and Mathematics)接替；此外，W3C还在全球各地建有14家办事机构，其中香港就有一处。

　　W3C的工作以成员机构为载体负责实施。截止目前，W3C在全球已有超过450家会员机构，并与其他国际标准化等多家组织机构建立了广泛的合作关系。此外W3C还有少量的专职工作人员，总共有70多人。

　　创建伊始，W3C就开始以引领Web 技术的发展和促进为己任。其宗旨概括为7点：
　　* 推进Web的普及，即希望未来无论任何人、任何设备、任何地点以及任何时间(4A)都可以方便地使用Web和Web上的合法资源。
　　* 解决语义网络(Semantic Web)问题，即不仅人能阅读和理解Web上的信息，计算机、程序以及其他硬件设备也 同样能理解并处理Web上的形形色色的 信息。
　　* Web应该是可信任的网络，使Web上的机密信息有安全保证、同时使用者得到的也是一个安全可靠的网络资源环境。
　　* 协同工作，W3C从成立之初就是一个厂商中立的技术组织，始终通过在工业上达成共识、鼓励开放性讨论来致力于设计、推广开放的语言，以及通过各种技术草案来推动基于Web的各类软件产品，从而避免市场上技术规范的混乱。
　　* 可持续发展问题。W3C的立足点是发展和推广基于Web的技术，由于网络的易用性等特点，W3C已清楚地意识到Web的需求总是走得更远，因此，为保证Web的可持续发展，所有的设计都遵循简易性、可调节性、兼容性、可扩展性等指导原则。
　　* 权利的分散问题。为避免人为和客观上造成的瓶颈和技术失衡问题，W3C的工作是分散处理的。
　　* 支持多媒体，由于Web本身就拥有极其丰富的资源，其中相当一部分是多媒体信息，因此，多媒体信息处理领域内的规范是W3C的一个重要方向。
　　
　　总之，W3C以开发“Web 事实标准”的各种技术规范作为其核心任务，目前已开发了超过50个技术规范。这些技术规范中大部分是由各个功能组开发的各种功能性规范，同时也包括WWW的核心体系结构。W3C的这些成果基本上已由企业和研究机构进行了实现。

　　基于W3C的组织原则和工作宗旨，以及Web的实际应用情况，W3C提出了其长远目标，包括3个方面的内容，分别是：
　　* 建立一个普遍的、全社会易于使用的公共网络环境；
　　* Web上的语义可管理和正确使用；
　　* Web应该是安全可信的。
　　
二、 W3C推出的主要规范
　　
　　到目前为止，W3C已开发了超过50个规范(草案)。这些规范(草案)包括人们早已、耳熟能详的HTML、HTTP、URIs、XML等，也包括针对语义Web的RDF、OWL等。W3C的已有工作成果和工作框架如 图1所示。
　　* HTML/XHTML：HTML是Web的基础之一，基于HTML，Web上开始出现丰富多彩的页面，蕴涵了各种信息。基于HTML，Web以一种简便易用的方式走出了象牙塔，成为全社会的公共资源和财富。W3C先后推出了多个HTML版本，分别是1997年12月的首个版本、1998年4月的更新、1999年12月推出HTML 4.01版。XHTML是对HTML 4.01的扩展，在其中可以使用XML的语义功能。XHTML 1.0已于2000年1月作为推荐标准发布；XHTML Basic是对XHTML1.0的独立于设备(如手机、PDA等)的扩展，于2000年12月发布；随后，2001年5月推出了XHTML的模块化版本——XHTML1.1。
　　* CSS：CSS负责为网页设计人员提供丰富的款式空间来设计网页。CSS所提供的网页结构内容与表现形式的分离机制，大大简化了网站的管理，提高了开发网站的工作效率。CSS可用于控制任何HTML和XML内容的表现形式。CSS1.0于1996年12月推出，1998年5月CSS2.0发布。
　　* XML:1998年2月发布的XML 1.0是W3C最具前瞻性和最有影响的标准之一。XML作为下一代Web的第一块重要基石，为分布式的、异构的数据交换提供了强大的功能，并且将数据本身和数据的表现分离，同时，就数据本身而言，数据的值和语义也是适当分离的。事实上，XML已经发展为一族技术，包括2001年5月发布的XML Schema、1999年1月发布的XML Namespaces、1999年11月发布的用于处理XML转换的XSLT和用于在XML文档中定位的XPath，以及2001年6月发布的XLink和XML Base等。此外，XML的出现为程序能够自动地处理Web数据和信息，以及Web服务(WSDL、SOAP、UDDI规范)提供了一种公共基础。
　　* DOM：DOM为HTML、XML等数据载体和信息载体在内存中的处理提供了一种基本的对象模型，可提供连接到文件的结构、格式、事件等。由于不依赖于任何程序设计语言和网页描述语言，它为有效处理HTML和XML数据提供了一种标准的、独立的接口。DOM先后经历了3个版本，分别是1998年10月发布的DOM Level 1、2000年11月发布的DOM Level 2和2003年发布的DOM Level 3。
　　* MathML：MathML为在Web上实现一种跨平台的数学描述机制提供了工具性语言。MathML先后推出过2个版本：1999年7月发布的MathML 1.0和2001年2月发布的MathML 2.0。
　　* PNG(Portable Network Graphics)：1996年发布的PNG是一种可移植的、对图形像素无影响的、便于图像压缩的图像文档格式。目前已是使用最广泛的Web图像格式之一。
　　* SVG(Scalable Vector Graphics)：SVG是针对Web上大量矢量图提供的图像内容管理机制，包括图像内容查询、定制和使用图像等功能。2001年9月推出的是SVG 1.0，SVG 1.1/SVG Basic和Tiny已经可以为一些小型设备提供矢量图像；2003年7月已提交SVG 1.2草案。
　　* RDF(Resource Description Framework)：RDF是第一个有关构建语义网络的推荐标准，它提供了一种技术标准来描述Web上的词汇、编码和元数据(Metadata)，并建立这些对象与Web上丰富资源之间的联系。RDF于1999年2月发布，至今仍是最重要的语义Web方面的技术标准，也是其他技术的基础之一。
　　
三、 W3C的未来工作重点
　　
　　毫无疑问，W3C未来的工作重点仍然一如既往地围绕其长远目标来展开。具体可分为Web Services、Semantic Web，以及这两者结合起来的Semantic Web Services。除此以外，基于各种移动设备(如手机等)的Web访问机制也是目前的研究热点。
　　
四、 中国的W3C现状
　　
　　中国已成为Web用户增长最快的国家，W3C也注意到这一点，因此最近两年，W3C的一些高层人物相继出访我国，与我国同行进行了广泛的交流，并在香港特别行政区已设立了办事处；我国的研究人员也对W3C的草案工作投入了极大关注，目前在这方面最为活跃的单位有中国科学院计算所、中国科学院软件所、清华大学、北京大学、北京科技大学、北京邮电大学、东南大学等研究机构；但遗憾的是各大软件公司虽然也积极关注W3C的各种活动和成果，却没有主动参与到国内同行的交流、国际草案的讨论、规范的制定中去，在技术上难免比较被动。
　　
　　2003年11月，由中国计算机学会、万维网联盟香港办事处主办，在北京中国科学院情报文献中心召开了W3C 2003中国论坛。以W3C总干事Ivar Herman为首的权威人士在语义Web、移动计算、国际化、网络可读性等方面进行了交流，并介绍了这几个领域的工作内容和研究现状。
编辑本段WEB标准
　　
　　WEB标准不是某一个标准，而是一系列标准的集合。网页主要由三部分组成：结构（Structure）、表现（Presentation）和行为（Behavior）。对应的标准也分三方面：结构化标准语言主要包括XHTML和XML，表现标准语言主要包括CSS，行为标准主要包括对象模型（如W3C DOM）、ECMAScript等。这些标准大部分由W3C起草和发布，也有一些是其他标准组织制订的标准，比如ECMA（European Computer Manufacturers Association）的ECMAScript标准。我们来简单了解一下这些标准：
　　
　　1．结构标准语言
　　（1）XML 
　　XML是The Extensible Markup Language(可扩展标识语言)的简写。目前推荐遵循的是W3C于2000年10月6日发布的XML1.0，参考（www.w3.org/TR/2000/REC-XML-20001006）。和HTML一样，XML同样来源于SGML，但XML是一种能定义其他语言的语。XML最初设计的目的是弥补HTML的不足，以强大的扩展性满足网络信息发布的需要，后来逐渐用于网络数据的转换和描述。关于XML的好处和技术规范细节这里就不多说了，网上有很多资料，也有很多书籍可以参考。
　　（2）XHTML 
　　XHTML是The Extensible HyperText Markup Language可扩展标识语言的缩写。目前推荐遵循的是W3C于2000年1月26日推荐XML1.0（参考http://www.w3.org/TR/xhtml1）。XML虽然数据转换能力强大，完全可以替代HTML，但面对成千上万已有的站点，直接采用XML还为时过早。因此，我们在HTML4.0的基础上，用XML的规则对其进行扩展，得到了XHTML。简单的说，建立XHTML的目的就是实现HTML向XML的过渡。
　　
　　2. 表现标准语言
　　CSS是Cascading Style Sheets层叠样式表的缩写。目前推荐遵循的是W3C于1998年5月12日推荐CSS2（参考http://www.w3.org/TR/CSS2/）。W3C创建CSS标准的目的是以CSS取代HTML表格式布局、帧和其他表现的语言。纯CSS布局与结构式XHTML相结合能帮助设计师分离外观与结构，使站点的访问及维护更加容易。
　　
　　3.行为标准
　　
　　（1）DOM
　　DOM是Document Object Model文档对象模型的缩写。根据W3C DOM规范（http://www.w3.org/DOM/），DOM是一种与浏览器，平台，语言的接口，使得你可以访问页面其他的标准组件。简单理解，DOM解决了Netscaped的Javascript和Microsoft的Jscript之间的冲突，给予web设计师和开发者一个标准的方法，让他们来访问他们站点中的数据、脚本和表现层对像。
　　
　　（2）ECMAScript
　　ECMAScript是ECMA(European Computer Manufacturers Association)制定的标准脚本语言（JAVAScript）。目前推荐遵循的是ECMAScript 262（http://www.ecma.ch/ecma1/STAND/ECMA-262.HTM）。
编辑本段W3C CSS验证器
　　这是什么？我需要它么？
　　W3C CSS验证服务是由W3C制作的一个免费软件，用于帮助Web设计者检查层叠样式表(CSS)。你可以在W3C提供的免费在线服务中使用，也可以下载后作为一个Java程序或者Servlet运行在自己的机器上。
　　你需要它么？如果你是一个web开发者或者web设计人员，这个工具将是一个强大的助手，它不仅会将你所写的css文件和css的标准进行比较，帮你找出错误，笔误，误用等等，它还可以告诉你你的css中可用性上的风险。
　　上面的解释我看不懂！求救！
　　大部分的网页是使用html的计算机语言编写的，这种语言能创建一个结构化划分信息，超链接，多媒体对象等。对于颜色，文字，布局等样式方面的问题，html采用css来解决，css是“层叠样式表”的简称。这个工具所做的事情就是帮助用户进行css的检查，并且在需要的时候可以做一些自动更正。
　　那么，这个东西是判断一个css是正确与否的权威么？
　　不，它只是一个有用的可靠的软件工具，和所有的软件一样，它也有自己的bug和问题。真正的权威应该参考css标准。
　　需要花费多少钱？
　　不需要。这个服务是免费的，并且源代码也是公开的，你可以自由的下载，使用，修改，分发等等。 如果你很喜欢它，我们也欢迎你加入这个项目，或者通过W3C的支持者程序来资助它，但是没有任何人可以强迫你这样做。
　　谁写了这个工具？谁在维护这个工具？
　　W3C维护并运行这个服务，感谢W3C的成员，志愿开发者和志愿翻译者所作的工作。更详细的信息请访问创作人员列表。你也可以加入进来。 
　　我能帮着做点什么呢？
　　当然，如果你是一个Java的编程人员，你可以通过取得源代码，添加你的新代码或者改正bug的代码。
　　除此之外，你也可以通过改进文档，翻译，加入mailinglist去解答别人的疑问来帮助这个工具。
　　还有别的问题？
　　如果你还有别的关于css或者css验证器的问题，请加入mailinglist或者论坛。但是在那之前，请仔细阅读一下css验证器的常见问题及解答(FAQ)，避免不必要的重复劳动和浪费别人的精力。
编辑本段W3C 技术架构图
　　W3C技术架构图描绘了一个两层的模型：万维网体系结构（被标注为“One Web”）建立在互联网(Interner)体系结构之上。图中丰富的Web层显示了W3C关心的领域和发展的技术。 
　　Web体系结构被描绘成一系列的层，每一层都建立在另一层之上。从底至顶依次为：
　　URI/IRI, HTTP 
　　Web Architectural Principles 
　　XML Infosets; RDF(S) Graphs 
　　XML, Namespaces, Schemas, XQuery/XPath, XSLT, DOM, XML Base, XPointer, RDF/XML, SPARQL 
　　在顶层包含着六个框，分别与W3C主要的活动组相对应：Web Applications, Mobile, Voice, Web Services, Semantic Web, and Privacy。
　　"Interaction"（“交互”）框中罗列着：XHTML, SVG, CDF, SMIL, XForms, css, 和 WCID. 
　　"Mobile"（“移动”）框中罗列着 XHTML Basic, Mobile SVG, SMIL Mobile, XForms Basic, css Mobile, MWI BP. 
　　"Voice"（“语音”）框中罗列着 VoiceXML, SRGS, SSML, CCXML, and EMMA 
　　"Web Services"（“Web服务”）框中罗列着 SOAP, XOP, WSDL, WS-CDL, and WS-A. 
　　"Semantic Web"（“语义的Web”）框中罗列着 OWL, SKOS, and RIF. 
　　"Privacy"（“保密”）框中罗列着 P3P, APPEL, XML Encryption, XML Signature, and XKMS 
　　一个橙色的横条把这些领域联系在一起：Web Accessibility（Web可访问性）, Internationalization（国际化）, Mobile Access（移动访问）, Device Independence（设备独立）, and Quality Assurance（质量保证）。
　　这个例图展示了万维网的基础框架及 W3C 的工作重点 。
　　URI、HTTP、XML 和 RDF 的基础支持著五个方面的工作。无障碍网页、国际化、设备无关和质量管理等主题已融入了 W3C 的各项技术之中。 
　　W3C正致力把万维网从最初的设计 (基本的 HTML、URIs 和 HTTP) 转变为未来所需的模式。 W3C 的技术将帮助未来万维网成为信息世界中有高稳定性、可提升和强适应性的基础框架。

