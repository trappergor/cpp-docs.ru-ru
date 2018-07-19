---
title: UUID (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- uuid_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e81b81509877ff53b613af80638b2386ed0cb0b2
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944807"
---
# <a name="uuid-c"></a>uuid (C++)
**Блок, относящийся только к системам Microsoft**  
  
 Компилятор добавляет идентификатор GUID для класса или структуры, объявленные или определенные (полного определения COM-объекта только) с **uuid** атрибута.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
__declspec( uuid("ComObjectGUID") ) declarator  
```  
  
## <a name="remarks"></a>Примечания  
 **Uuid** атрибут принимает в качестве аргумента строку. Эта строка именует идентификатор GUID в обычном формате реестра с или без **{}** разделители. Пример:  
  
```cpp 
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 Этот атрибут можно применить при повторном объявлении. Это позволяет заголовкам системы предоставлять определения интерфейсов, таких как `IUnknown`и гарантировать повторное объявление в другом заголовке (такие как \<comdef.h >) для предоставления идентификатора GUID.  
  
 Ключевое слово [__uuidof](../cpp/uuidof-operator.md) могут применяться для извлечения постоянного идентификатора GUID для определяемого пользователем типа.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)