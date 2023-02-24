---
title: "Extract Information From PDFs"
date: 2023-02-23T15:13:27+01:00
showtoc: false
tags: ["OCR", "image2text"]
unsafe: true
---


# tl;dr 
> Optical Character Recognition (OCR) can be used to extract text information from PDF files. In this blog post, I am using the [*tesseract*](https://github.com/tesseract-ocr/tesseract) framework to extract the weekly menu of a takeaway store.

---

# What am I using OCR for?
For a side project, I am creating a lunch web app. The goal is to provide an overview of all lunch menus in the proximity. I am setting up the web app for my home city to kick off the project. 

{{< rawhtml>}}
<figure>
    <img src="/tesseract/lunch.png" style="height:500px;margin:auto;display:block">
</figure>
<div align="center"><i>Image generated with Midjourney</i></div>
<br>
{{< /rawhtml>}}

One popular takeaway chain in my home city is publishing its weekly menu using a PDF file. I am using Machine Learning to extract the information from the PDF file in an automated fashion. 

# Here are the results:

The following image shows the menu from last week:
![takeaway](/tesseract/take-away.png "Test")
{{< rawhtml >}}
<div align="center"><i>Weekly menu in German. (Click to enlarge)</i></div>
{{< /rawhtml >}}

In this example, I use the [*tesseract*](https://github.com/tesseract-ocr/tesseract) framework to perform OCR. Here is the extracted text from the image above:


```
Meuuplaa

Mittags-Augebote Bake off-Hit

Montag Penne AN Vom 13. bis 19. Februar 2023
13. Februar 2023 mit Vegi-Bolognese

8.80 Vegi Calzone Caprese

4.90

Dienstag Kartoffelpfanne Bauernart
14. Februar 2023 mit Speck und Zwiebeln

8.80

Herkunft Schweinefleisch: Schweiz
Mittwoch Massaman Curry AN
15. Februar 2023 mit Cashewnut, Rosinen

und Jasminreis Vegi

8.80 F
Donnerstag Älpler Magronen
16. Februar 2023 mit Röstzwiebeln

8.80

PET-Getränk
in Kombination mit einem Sandwich

Freitag Thai Nudelwok oder Salat nach Ihrer Wahl für nur
17. Februar 2023 mit Poulet

und asiatischem Gemüse + 1.50

8.80

Herkunft Geflügel: Schweiz

Änderungen vorbehalten. Angebot in der Genossenschaft Migros Ostschweiz gültig. Mittags-Menu nicht in den takeaways Rorschach, Münchwilen,
OBlI Grüzepark und OBI St. Gallen erhältlich.

TAKE AWAY
```
Overall, the OCR process did a great job.
The extracted text contains some errors. E.g., **Meuuplaa** was identified instead of **Menuplan**. The errors stem from the particular font used in the PDF for the titles. The underlying model could be fine-tuned to improve the results for this specific font.

However, for my purposes, the OCR performance is fine. I am just interested in the printed text, which is accurately identified.

# How does it work? 

To get the results, the following steps are performed:

1. Convert PDF file to PNG image 

   (tesseract expects image formats like *png, jpg, tiff*)
2. Identification of relevant areas on the image  (text detection)
3. Convert image parts to text (text transcription)
4. Postprocessing of the output

I won't dive into the details here. But steps **2 & 3** are performed by tesseract internally. Two separate models perform the text detection and text transcription tasks. 

I adjusted the original image to show the tesseract results to highlight this.

![ocr_results](/tesseract/ocr_results.png)
{{< rawhtml >}}
<div align="center"><i>OCR results shown on the original image</i></div>
{{< /rawhtml >}}

# That's it

This was a short intro to OCR using tesseract and my first blog post on this page :smile:.