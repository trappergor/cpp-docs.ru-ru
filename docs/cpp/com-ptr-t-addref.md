---
title: _com_ptr_t::AddRef | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::AddRef
dev_langs:
- C++
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54a1b629f254bae2b72790546bcbb00185f2c44c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef
**Блок, относящийся только к системам Microsoft**  
  
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