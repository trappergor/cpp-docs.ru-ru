---
title: "Поддержка COM компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
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
ms.openlocfilehash: d81c54f7af604024da852999ca78fa5ee55079ef
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="compiler-com-support"></a>Поддержка COM компилятора
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Компилятор Visual C++ может непосредственно считать библиотеки типов COM-модели и преобразовать их содержимое в исходный код С++б который можно включить в компиляцию. Расширения языка позволяют выполнять программирование COM-модели на клиентской стороне.  
  
 С помощью [директиву препроцессора #import](../preprocessor/hash-import-directive-cpp.md), компилятор может прочитать библиотеку типов и преобразовать его в файл заголовка C++, который описывает COM интерфейсы как классы. Набор атрибутов `#import` доступен для пользовательского контроля содержимого в полученных файлах заголовка библиотеки типов.  
  
 Можно использовать [__declspec](../cpp/declspec.md) расширенный атрибут [uuid](../cpp/uuid-cpp.md) присвоить глобальный уникальный идентификатор (GUID) для COM-объекта. Ключевое слово [__uuidof](../cpp/uuidof-operator.md) можно использовать для извлечения идентификатора GUID, связанный с COM-объекта. Другой `__declspec` атрибут, [свойство](../cpp/property-cpp.md), можно использовать для указания **получить** и **задать** методы для элемента данных COM-объекта.  
  
 Набор глобальных функций поддержки COM и классов обеспечивает поддержку **VARIANT** и `BSTR` типы, реализации интеллектуальных указателей и инкапсуляции объекта ошибок, вызванных `_com_raise_error`:  
  
-   [Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)  
  
-   [_bstr_t](../cpp/bstr-t-class.md)  
  
-   [_com_error](../cpp/com-error-class.md)  
  
-   [_com_ptr_t](../cpp/com-ptr-t-class.md)  
  
-   [_variant_t](../cpp/variant-t-class.md)  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Классы поддержки компилятора COM](../cpp/compiler-com-support-classes.md)   
 [Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)
