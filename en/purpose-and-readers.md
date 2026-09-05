<!-- source: この文書の目的・対象読者.md 2026-09-04 -->

# Chapter 1. Purpose and Intended Readers

> This chapter describes what this document is, why it is needed, and why you should read it.

> A very brief statement of what this document is.

This document addresses what is needed to correctly author Japanese text and to present it legibly in text whose display adapts to the reader's environment. Web pages, email, and UI text are examples. In this document, such text—encompassing its data, presentation, and dynamic behavior as a whole—is called digital text.

Documents that have a fixed, page-by-page presentation and do not adapt to the reader's environment, such as PDF, are outside the scope of this document. For these, see "Requirements for Japanese Text Layout" (JLReq). The boundary, however, is not absolute. Reflowable e-books, while paginated, adapt their presentation to the display environment, so much of this document applies to them. Even documents with a fixed presentation may benefit from this document—particularly the chapters for authors—during the process of creating them on a digital device.

## 1. Purpose of This Document

> Why this document is needed. Concise but compelling.

Print and digital text share the same goal, yet rest on entirely different technological foundations. The most fundamental difference between them is who determines the final image. In print, the sender creates an image from materials such as text, and delivers that single image to every reader. In digital text, what the sender transmits is the materials—text and others—together with presentation instructions; the final image is generated at the reader's end, shaped by the characteristics of their device, their preferences, and their needs. A single transmission gives rise to countless different images.

From this difference, digital text acquires several properties that print does not have. The most important is that it can adapt to each individual user. As the other side of this coin, the sender cannot know the result in advance. Furthermore, text remains live data even after it has been read, subject to operations such as selection, search, cut-and-paste, and the application of different styles.

The rules for Japanese text layout in use today were established under the technology of metal movable type, as rules for producing legible and beautiful printed matter with economic efficiency. They therefore strongly reflect the constraints of metal type and the properties of paper as a medium. Because of the difference in technological foundations, attempting to apply these rules directly to digital devices reveals various problems and gaps. What print has aimed for is text that is effortless to read and beautiful. The aim for digital should be the same—imitating print is not the objective.

When a new technological foundation emerges, what is first realized on it is, more often than not, an imitation of the previous technology. PDF and word processors are examples: they were born to reproduce the appearance of print on digital devices. Just as the early automobile took the form of a horse-drawn carriage, a new technology starts by borrowing the old form and eventually discovers a form suited to its own possibilities.

This document addresses text beyond print. Why it does not address pages, for example, becomes clear by tracing the history of the codex. The codex was an invention whose impact rivaled that of printing itself. It was rectangular and easy to store, its spine made it possible to survey a collection at a glance, and page numbers enabled random access. Digital devices, however, inherently provide storage, search, and random access over data. Most of the advantages of the codex lose their significance in the digital world, and the dominant form has become scrolling—reading as one would a scroll—as seen on the Web and in email.

In addition to the difference in technological foundations, the environment surrounding the technology has also changed. Software development, including for the Web, now takes place on an international stage; much of the work of shaping the appearance of text, once handled by specialists, has shifted to the authors themselves; and ensuring accessibility has become critically important.

Against this background, this document updates the conventional rules and the way they are described as necessary, and extends them for capabilities unique to digital text, such as its dynamic behavior. In addition, because so much of this work has shifted to the authors themselves as noted above, a set of chapters for authors has been included. Furthermore, because the way individual fonts are functionally built has a significant impact on the presentation of digital text, this document also addresses font-related requirements.

In writing this document, we have tried to explain the reasons and background as fully as possible, so that it may serve as an aid in devising better solutions. We hope that it will help achieve more sophisticated layout and display of Japanese text on digital devices, and help carry Japanese text into the future.

Whereas the previously published "Requirements for Japanese Text Layout" (JLReq) describes the already established rules for text layout in print, this document discusses text layout and display in a digital environment that is evolving day by day. As digital devices and digital text continue to evolve, this document too will need to incorporate those developments.

## 2. Intended Readers

This document is written for everyone who works with Japanese on digital devices. Namely:

#### People who author Japanese text

As noted above, much of the work of shaping the appearance of text has shifted to the authors themselves, and this document accordingly addresses people who author Japanese text. This includes people who write Japanese as part of their daily life as native speakers, as well as people who are not necessarily familiar with Japanese but handle Japanese localization at international companies, among others. In most cases, digital text reaches its readers without passing through professional proofreading. By reading the authoring chapters, authors can acquire the knowledge needed to make decisions that were once left to specialists—such as how to choose characters and fonts, and how to create a legible presentation.

#### People who implement the display of Japanese text

As with JLReq, this document addresses engineers involved in the development of standards, design, and implementation of text-related software. To ensure that even engineers with little or no knowledge of Japanese can understand, the authoring chapters explain the fundamentals, including how the Japanese writing system works, and the implementation chapters show what text-related software needs to do. That said, development is a continuous series of judgments, and engineers who deeply understand Japanese and its market remain indispensable.

#### People who fine-tune the appearance of Japanese text

The implementation chapters are also useful for those who need to fine-tune the presentation of text in documents or websites that include Japanese—designers and front-end engineers, for example. The APIs of digital devices and design tools offer great flexibility over text presentation, but taking advantage of that flexibility requires knowledge of the principles and mechanisms of text layout. However, this document does not address individual design choices.

### AI

Because this document will be published as an official W3C technical document, it is expected that AI systems such as large language models will refer to it as a basis for generating Japanese text and making decisions about its presentation. Referring not only to the methods described herein but also to their reasons and background will enable appropriate decisions tailored to individual situations. With this in mind, we have striven for descriptions that allow mechanically precise interpretation—in the definition of terms, the relationships between concepts, the specification of conditions, and elsewhere.

## 3. How to Read This Document

This document is divided into authoring chapters and implementation chapters. Authors can obtain the knowledge they need from the authoring chapters alone. The implementation chapters are aimed at software designers and implementers, but are also useful for readers such as designers who need to fine-tune text presentation beyond the ordinary.

In terminology, internationally recognized concepts and terms are preferred over specialist printing terminology from Japan. (Examples to be added.)

Where multiple methods exist, one is presented as the standard method, with an explanation of why it was chosen and the background behind the decision. Reasons are provided so that readers can make different judgments as their circumstances require. Methods for achieving higher quality are also introduced, showing a path toward better results. How far to implement depends on the purpose of the application—a text editor and an e-book reader, for example, demand different levels. Accordingly, the importance of each feature is explained together with the conditions under which it applies.

Accessibility is woven into the relevant sections throughout, not only treated as a separate topic. Where standards or implementations for text layout are lacking, this is explicitly noted.

This document does not venture into text layout that is not specific to Japanese (foreign languages including those using the Latin script, mathematical expressions, subscripts and superscripts, units, and so on). Where text in other languages meets Japanese text, only the behavior at that boundary is defined.