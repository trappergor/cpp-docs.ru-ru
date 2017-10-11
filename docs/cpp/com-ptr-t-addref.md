---
title: "_com_ptr_t::AddRef | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::AddRef
dev_langs:
- C++
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d873d91192dc13f7b1277cbe8ef26b24421b6904
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef
**Блок, относящийся только к системам Майкрософт**  
  
 Вызовы `AddRef` функцию-член **IUnknown** на инкапсулированный указатель на интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
void AddRef( );  
  
```  
  
## <a name="remarks"></a>Примечания  
 Вызовы `IUnknown::AddRef` на инкапсулированный указатель на интерфейс, вызов `E_POINTER` ошибки, если указатель находится **NULL**.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
