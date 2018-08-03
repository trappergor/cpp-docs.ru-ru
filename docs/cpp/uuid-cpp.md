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
ms.openlocfilehash: 93ae3ac7f0d6fff700e1c89aad197d5f03734cf5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467112"
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