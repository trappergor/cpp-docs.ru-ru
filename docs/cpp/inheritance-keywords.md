---
title: "Ключевые слова наследования | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __multiple_inheritance
- __single_inheritance_cpp
- __virtual_inheritance_cpp
- __virtual_inheritance
- __multiple_inheritance_cpp
- __single_inheritance
dev_langs:
- C++
helpviewer_keywords:
- __single_inheritance keyword [C++]
- declaring derived classes
- keywords [C++], inheritance keywords
- __multiple_inheritance keyword [C++]
- __virtual_inheritance keyword [C++]
- inheritance, declaring derived classes
- derived classes, declaring
- inheritance, keywords
ms.assetid: bb810f56-7720-4fea-b8b6-9499edd141df
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6286d8e3082f0a4a3ce3e00fb3de1ad4ca41589a
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="inheritance-keywords"></a>Ключевые слова наследования
**Блок, относящийся только к системам Майкрософт**  
  
```  
  
class [__single_inheritance] class-name;class [__multiple_inheritance] class-name;class [__virtual_inheritance] class-name;  
```  
  
 где:  
  
 *Имя класса*  
 Имя объявляемого класса.  
  
 В C++ указатель на член класса можно объявить до определения класса. Пример:  
  
```  
class S;  
int S::*p;  
```  
  
 В представленном выше коде `p` объявляется как указатель на целочисленный член класса S. Однако `class S` имеет еще не определен в этом коде; он только объявлен. Когда компилятор обнаруживает такой указатель, он должен создать обобщенное представление указателя. Размер представления зависит от указанной модели наследования. Указать модель наследования для компилятора можно четырьмя способами.  
  
-   В Интегрированной среде разработки под **представление указателя на член**  
  
-   В командной строке с помощью [/vmg](../build/reference/vmb-vmg-representation-method.md) переключения  
  
-   С помощью [pointers_to_members](../preprocessor/pointers-to-members.md) директивы pragma  
  
-   С помощью ключевых слов наследования `__single_inheritance`, `__multiple_inheritance` и `__virtual_inheritance`. При использовании этого метода управление моделью наследования осуществляется на уровне класса.  
  
    > [!NOTE]
    >  Если указатель на член класса всегда объявляется после определения класса, нет необходимости использовать какой-либо из этих параметров.  
  
 Объявление указателя на член класса до определения класса влияет на размер и скорость полученного исполняемого файла. Чем сложнее наследование, используемое в классе, тем больше число байтов, требуемых для представления указателя на член класса, и тем больше код, необходимый для интерпретации указателя. Одиночное наследование является самым простым, а виртуальное наследование — самым сложным.  
  
 Если приведенный выше пример изменить на  
  
```  
class __single_inheritance S;  
int S::*p;  
```  
  
 независимо от параметров командной строки или директив pragma указатели на члены `class S` будут использовать наименьшее возможное представление.  
  
> [!NOTE]
>  То же опережающее объявление представления указателя на член должно быть включено в каждую запись преобразования, которая объявляет указатели на члены этого класса, и объявление должно выполняться до объявления указателей на члены.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)
