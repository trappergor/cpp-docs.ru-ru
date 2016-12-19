---
title: "Ошибка средств компоновщика LNK2005 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2005"
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK2005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

символ уже определен в объекте  
  
 Указанный символ `symbol`, отображаемый в декорированном виде, был определен несколько раз.  
  
 Подробнее см. в следующих статьях базы знаний.  
  
-   "Ошибка LNK2005 возникает, когда библиотеки CRT и библиотеки MFC связаны в неправильном порядке в Visual C\+\+" \(148652\)  
  
-   "Глобальный перегруженный оператор delete вызывает ошибку LNK2005" \(140440\)  
  
-   "Операторы new и delete вызывают ошибки LNK2005 при определении \_ATL\_MIN\_CRT" \(184235\)  
  
 Статьи базы знаний можно найти на компакт\-диске библиотеки MSDN или на веб\-сайте [http:\/\/support.microsoft.com\/search](http://support.microsoft.com/search).  
  
 Эта ошибка сопровождается неустранимой ошибкой [LNK1169](../Topic/Linker%20Tools%20Error%20LNK1169.md).  
  
### Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Смешивание статических и динамических библиотек при одновременном использовании [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
2.  Символ является упакованной функцией \(созданной путем компилирования с параметром [\/Gy](../../build/reference/gy-enable-function-level-linking.md)\) и был включен более чем в один файл, но изменен в промежутке между компиляциями.  Перекомпилируйте все файлы, включающие `symbol`.  
  
3.  Символ определен по\-разному в двух объектах\-членах в различных библиотеках, и оба объекта\-члена используются.  
  
4.  Абсолютное значение определено дважды с различными значениями.  
  
5.  Файл заголовка объявлен и определен как переменная.  Ниже представлены возможные решения.  
  
    -   Объявите переменную в H\-файле: `extern BOOL MyBool;`, а затем присвойте ей значение в C\-файле или CPP\-файле: `BOOL MyBool = FALSE;`.  
  
    -   Объявите переменную как [static](../../misc/static-cpp.md).  
  
    -   Объявите переменную как [selectany](../../cpp/selectany.md).  
  
6.  Вы используете uuid.lib в сочетании с другими файлами LIB, определяющими идентификаторы GUID \(например oledb.lib и adsiid.lib\).  Например:  
  
    ```  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     Для исправления ошибки добавьте параметр [\/FORCE:MULTIPLE](../../build/reference/force-force-file-output.md) в параметры командной строки компоновщика и убедитесь в том, что uuid.lib является первой библиотекой в ссылках.