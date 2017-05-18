---
title: "Построение объектов потока вывода | Документы Майкрософт"
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
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
caps.latest.revision: 9
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
ms.openlocfilehash: ca8d4e9a44f4550d02e6d224ce0130d15e81da14
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="constructing-output-stream-objects"></a>Построение объектов потока вывода
Если используются только стандартные объекты `cout`, `cerr` или `clog`, не требуется создавать поток вывода. Необходимо использовать конструкторы для:  
  
- [конструкторов потока выходного файла](#vclrfoutputfilestreamconstructorsanchor1);  
  
- [конструкторов потока выходной строки](#vclrfoutputstringstreamconstructorsanchor2).  
  
##  <a name="vclrfoutputfilestreamconstructorsanchor1"></a> Конструкторы потока выходного файла  
 Вы можете создать поток выходного файла одним из двух следующих способов.  
  
-   Используйте конструктор по умолчанию, а затем вызовите функцию-член `open`.  
  
 ```  
    ofstream myFile; // Static or on the stack  
    myFile.open("filename");

 
    ofstream* pmyFile = new ofstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   Укажите имя файла и флаги режима в вызове конструктора.  
  
 ```  
    ofstream myFile("filename", ios_base::out);
```  
  
##  <a name="vclrfoutputstringstreamconstructorsanchor2"></a> Конструкторы потока выходной строки  
 Чтобы создать поток выходной строки, можно использовать `ostringstream` следующим образом.  
  
```  
    using namespace std;  
string sp;  
ostringstream myString;  
myString <<"this is a test" <<ends;  
sp = myString.str();
// Obtain string  
cout <<sp <endl;   
```  
  
 "Манипулятор" `ends` добавляет в строку необходимый завершающий нуль-символ.  
  
## <a name="see-also"></a>См. также  
 [Потоки вывода](../standard-library/output-streams.md)


