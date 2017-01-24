---
title: "Программирование с использованием CComBSTR (ATL) | Microsoft Docs"
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
  - "CComBSTR - класс, программирование с"
  - "Юникод, использование CComBSTR [ATL]"
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Программирование с использованием CComBSTR (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс [CComBSTR](../atl/reference/ccombstr-class.md) библиотеки ATL предоставляет программу\-оболочку для типа данных `BSTR`.  При `CComBSTR` эффективный инструмент, существует несколько ситуаций, требующих предосторежения.  
  
-   [Проблемы преобразования](#programmingwithccombstr_conversionissues)  
  
-   [Проблемы областей](#programmingwithccombstr_scopeissues)  
  
-   [Явное освобождение объект CComBSTR](#programmingwithccombstr_explicitlyfreeing)  
  
-   [Использование объектов CComBSTR в циклах](#programmingwithccombstr_usingloops)  
  
-   [Проблемы утечки памяти](#programmingwithccombstr_memoryleaks)  
  
##  <a name="programmingwithccombstr_conversionissues"></a> Проблемы преобразования  
 Хотя несколько методов `CComBSTR` автоматически преобразуют зашнуруйте аргумент ANSI в Юникод, методы всегда будет возвращать строки формата Юникода.  Для преобразования строки вывода обратно в ANSI, используйте класс преобразования библиотеки ATL.  Дополнительные сведения о классах преобразования библиотеки ATL см. в разделе [Макросы преобразования строки библиотеки ATL и MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
### Пример  
 [!CODE [NVC_ATL_Utilities#114](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#114)]  
  
 Если используется строковый литерал, чтобы изменить объект `CComBSTR` следует использовать широкие символьной строки.  Это уменьшит ненужные преобразования.  
  
### Пример  
 [!CODE [NVC_ATL_Utilities#115](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#115)]  
  
##  <a name="programmingwithccombstr_scopeissues"></a> Проблемы областей  
 Как и с любым хорошо\- поступаемым классом, `CComBSTR` освободит его ресурсы, когда он переместится из области.  Если функция возвращает указатель на строку `CComBSTR`, то это может привести к возникновению проблем, когда указатель будет ссылаться на память, которая уже была освобождена.  В подобных случаях можно использовать метод **Копировать**, как показано ниже.  
  
### Пример  
 [!CODE [NVC_ATL_Utilities#116](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#116)]  
  
##  <a name="programmingwithccombstr_explicitlyfreeing"></a> Явное освобождение объект CComBSTR  
 Возможно явно освобождать строку, содержащихся в объекте `CComBSTR`, прежде чем объект выходит за пределами области.  Если строки освобождается, то объект `CComBSTR` недопустим.  
  
### Пример  
 [!CODE [NVC_ATL_Utilities#117](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#117)]  
  
##  <a name="programmingwithccombstr_usingloops"></a> Использование объектов CComBSTR в циклах  
 По мере того, как класс `CComBSTR` выделяет буфер для выполнения различных операций, например оператор `+=` или метод **Добавление**, не рекомендуется выполнить манипуляцию строки в плотного цикла.  В этих случаях `CStringT` обеспечивает более высокую производительность.  
  
### Пример  
 [!CODE [NVC_ATL_Utilities#118](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#118)]  
  
##  <a name="programmingwithccombstr_memoryleaks"></a> Проблемы утечки памяти  
 Передача адрес, инициализированный `CComBSTR` функции в качестве параметра **\[out\]** вызовет утечку памяти.  
  
 В примере, приведенном ниже, протечена строка, выделенная для хранения строки `"Initialized"`, если функция `MyGoodFunction` заменяет строки.  
  
 [!CODE [NVC_ATL_Utilities#119](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#119)]  
  
 Во избежание утечки, вызовите метод **Пусто** на существующие объекты `CComBSTR` перед передачей адрес в качестве параметра **\[out\]**.  
  
 Обратите внимание, что один и тот же код не вызвал утечку если параметр функции было **\[in, out\]**.  
  
## См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)   
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)   
 [wstring](../Topic/wstring.md)   
 [String Conversion Macros](../atl/reference/string-conversion-macros.md)