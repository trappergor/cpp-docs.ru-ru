---
title: "naked (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- naked_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: daa03ee746de422f96e8f39dc451a71da2e0259c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="naked-c"></a>naked (C++)
**Блок, относящийся только к системам Microsoft**  
  
 Код функций, объявленных с атрибутом `naked`, создается компилятором без кода пролога и эпилога. Эту возможность можно использовать, чтобы создавать свой собственный код на языке ассемблера и вставлять его в качестве пролога и эпилога. Функции с атрибутом naked особенно полезны для написания драйверов виртуальных устройств.  Обратите внимание, что атрибут `naked` допускается только для архитектур x86 и ARM; на платформе [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] он недоступен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__declspec(naked) declarator  
```  
  
## <a name="remarks"></a>Примечания  
 Поскольку `naked` атрибут относится только к определению функции и не является модификатором типа, функции с атрибутом naked должны использовать расширенный синтаксис атрибутов и [__declspec](../cpp/declspec.md) ключевое слово.  
  

 Компилятор не может создать подставляемую функцию для функции, помеченной атрибутом naked, даже если функция помечена также [__forceinline](inline-functions-cpp.md) ключевое слово.  

  
 Если атрибут `naked` применяется не к методу, не являющемуся членом, а к любому другому объекту, то компилятор выводит ошибку.  
  
## <a name="examples"></a>Примеры  
 В следующем коде определена функция с атрибутом `naked`:  
  
```  
__declspec( naked ) int func( formal_parameters ) {}  
```  
  
 Другой пример.  
  
```  
#define Naked __declspec( naked )  
Naked int func( formal_parameters ) {}  
```  
  
 Атрибут `naked` влияет только на создание кода компилятора для последовательностей пролога и эпилога функции. Код, который создается для вызова таких функций, не зависит от этого атрибута. Таким образом, атрибут `naked` не входит в тип функции, а указатели на функции не могут иметь атрибут `naked`. Кроме того, атрибут `naked` не может применяться к определениям данных. Например, следующий код вызывает ошибку:  
  
```  
__declspec( naked ) int i;       // Error--naked attribute not  
                                 // permitted on data declarations.  
```  
  
 Атрибут `naked` относится только к определению функции и не может быть определен в прототипе функции. Например, следующее объявление создает ошибку компилятора:  
  
```  
__declspec( naked ) int func();  // Error--naked attribute not   
                                 // permitted on function declarations  
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Вызовы функций с атрибутом naked](../cpp/naked-function-calls.md)