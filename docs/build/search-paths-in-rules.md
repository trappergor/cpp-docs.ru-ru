---
title: "Пути поиска в правилах | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "правила вывода (NMAKE)"
  - "правила, вывод"
  - "пути поиска - правила вывода (NMAKE)"
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Пути поиска в правилах
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

```  
{frompath}.fromext{topath}.toext:  
   commands  
```  
  
## Примечания  
 Правило вывода применимо к зависимости только в том случае, если пути, указанные в зависимости, в точности соответствуют путям правила вывода.  Каталог зависимого объекта задается в параметре *frompath*, а каталог целевого объекта задается в параметре *topath*; пробелы не допускаются.  Для каждого разрешения указывается только один путь.  Наличие пути у одного расширения требует наличия пути у другого.  Чтобы указать текущий каталог, следует использовать точку \("."\) или пустые фигурные скобки \("{ }"\).  Пути *frompath* и *topath* могут представляться макросами; они вызываются в ходе предобработки.  
  
## Пример  
  
### Код  
  
```  
{dbi\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUDBI) $<  
  
{ilstore\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{misc\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{misc\}.c{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{msf\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{bsc\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{mre\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{namesrvr\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{src\cvr\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
```  
  
## См. также  
 [Определение правила](../build/defining-a-rule.md)