---
title: "Ошибка средств компоновщика LNK2005 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2005
dev_langs:
- C++
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: bf93f364b3dc7156a62eb1c474177eb7b85c7827
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2005"></a>Ошибка средств компоновщика LNK2005
символ уже определен в объекте  
  
Указанный символ `symbol`, отображаемый в декорированном виде, был определен несколько раз.  
  
Подробнее см. в следующих статьях базы знаний.  
  
-   [Ошибка LNK2005 возникает, когда библиотеки CRT и библиотеки MFC связаны в неправильном порядке в Visual C++](https://support.microsoft.com/kb/148652)  
  
-   [Исправление: Глобальное удаление перегруженный оператор причины LNK2005](https://support.microsoft.com/kb/140440)  
  
-   [При компиляции проекта ATL исполняемый файл (.exe) в Visual C++ ошибки LNK2005](https://support.microsoft.com/kb/184235).  
  
Эта ошибка сопровождается неустранимой ошибки [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md).  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Смешивание статических и динамических библиотек при одновременном использовании [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
2.  Символ является упакованной функцией (созданной компилированием с [/Gy](../../build/reference/gy-enable-function-level-linking.md)) и был включен в более чем один файл, но изменен в промежутке между компиляциями. Перекомпилируйте все файлы, включающие `symbol`.  
  
3.  Символ определен по-разному в двух объектах-членах в различных библиотеках, и оба объекта-члена используются.  
  
4.  Абсолютное значение определено дважды с различными значениями.  
  
5.  Файл заголовка объявлен и определен как переменная. Ниже представлены возможные решения.  
  
    -   Объявите переменную в H-файле: `extern BOOL MyBool;`, а затем присвойте ей значение в C-файле или CPP-файле: `BOOL MyBool = FALSE;`.  
  
    -   Объявите переменную [статических](../../cpp/storage-classes-cpp.md#static).  
  
    -   Объявите переменную [selectany](../../cpp/selectany.md).  
  
6.  Вы используете uuid.lib в сочетании с другими файлами LIB, определяющими идентификаторы GUID (например oledb.lib и adsiid.lib). Например:  
  
    ```  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     Чтобы устранить проблему, добавьте [/FORCE: Multiple](../../build/reference/force-force-file-output.md) параметры командной строки компоновщика и убедитесь в том, что uuid.lib является первой библиотекой в ссылках.
