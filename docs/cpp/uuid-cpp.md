---
title: "UUID (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: uuid_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2a2e7ccf1074393a4f71f5d55155cd7e14b5d9f9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="uuid-c"></a>uuid (C++)
**Блок, относящийся только к системам Майкрософт**  
  
 Компилятор добавляет идентификатор GUID в класс или структуру, объявленные или определенные (только полные определения COM-объекта) с атрибутом `uuid`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
__declspec( uuid("  
ComObjectGUID  
") ) declarator  
```  
  
## <a name="remarks"></a>Примечания  
 Атрибут `uuid` принимает строку в качестве аргумента. Эта строка именует идентификатор GUID в обычном формате реестра с или без **{}** разделители. Пример:  
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 Этот атрибут можно применить при повторном объявлении. Это позволяет заголовкам системы предоставлять определения интерфейсов, например **IUnknown**и гарантировать повторное объявление в другом заголовке (например, COMDEF. (H) для предоставления идентификатора GUID.  
  
 Ключевое слово [__uuidof](../cpp/uuidof-operator.md) может применяться для извлечения постоянного идентификатора GUID, добавленного определяемого пользователем типа.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)