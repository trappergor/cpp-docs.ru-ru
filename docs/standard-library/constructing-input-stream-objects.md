---
title: "Построение объектов входного потока | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7e8c664bd6632f480ba53b9dedea914bbc8e4dd7
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="constructing-input-stream-objects"></a>Построение объектов потока ввода
Если используется только стандартный объект `cin`, не требуется создавать входной поток. Вы должны создавать входной поток, если используете:  
  
- [Конструкторы потока входного файла](#vclrfinputfilestreamconstructorsanchor8)  
  
- [Конструкторы потока входной строки](#vclrfinputstringstreamconstructorsanchor9)  
  
##  <a name="vclrfinputfilestreamconstructorsanchor8"></a> Конструкторы потока входного файла  
 Существует два способа создания потока входного файла.  
  
-   Используйте конструктор аргумента `void`, а затем вызовите функцию-член `open`:  
  
 ```  
    ifstream myFile; // On the stack  
    myFile.open("filename");

 
    ifstream* pmyFile = new ifstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   Укажите имя файла и флаги режима в вызове конструктора, тем самым открывая файл во время процесса построения:  
  
 ```  
    ifstream myFile("filename");
```  
  
##  <a name="vclrfinputstringstreamconstructorsanchor9"></a> Конструкторы потока входной строки  
 В конструкторах потока входной строки требуется адрес предварительно выделенного и предварительно инициализированного хранилища:  
  
```  
string s("123.45");

double amt;  
istringstream myString(s);

//istringstream myString("123.45") also works  
myString>> amt; // amt contains 123.45  
```  
  
## <a name="see-also"></a>См. также  
 [Потоки ввода](../standard-library/input-streams.md)


