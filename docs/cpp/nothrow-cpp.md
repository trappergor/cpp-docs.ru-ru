---
title: "nothrow (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- nothrow_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
caps.latest.revision: 7
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
ms.openlocfilehash: c74490229e2ef54e7947f5e8fedda6057ecccb70
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="nothrow-c"></a>nothrow (C++)
**Блок, относящийся только к системам Майкрософт**  
  
 Расширенный атрибут `__declspec`, который может быть использован в объявлении функций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
return-type __declspec(nothrow) [call-convention] function-name ([argument-list])  
```  
  
## <a name="remarks"></a>Примечания  
 Этот атрибут сообщает компилятору, что и объявленная функция, и функции, которые она вызывает, никогда не создают исключений. Поскольку по умолчанию теперь используется модель синхронной обработки исключений, то компилятор может исключить механизм, позволяющий отслеживать время существования удаляемых объектов в такой функции, и значительно уменьшить объем кода. В следующей директиве препроцессора все три объявления функций эквивалентны:  
  
```  
#define WINAPI __declspec(nothrow) __stdcall   
  
void WINAPI f1();  
void __declspec(nothrow) __stdcall f2();  
void __stdcall f3() throw();  
```  
  
 Объявление `void __declspec(nothrow) __stdcall f2();` имеет то преимущество, что оно позволяет использовать определение API (в нашем примере это сделано при помощи оператора `#define`), чтобы легко задать ключевое слово `nothrow` для набора функций. Третье объявление`, void __stdcall f3() throw();` имеет синтаксис, определенный стандартом C++.  
  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
