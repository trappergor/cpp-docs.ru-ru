---
title: _com_ptr_t::AddRef | Документация Майкрософт
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
ms.openlocfilehash: 4bf56e87b8b7949048b1e6006d3aa32f00af1462
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404263"
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef
**Блок, относящийся только к системам Microsoft**  
  
 Вызовы `AddRef` функцию-член `IUnknown` на инкапсулированный указатель на интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void AddRef( );  
```  
  
## <a name="remarks"></a>Примечания  
 Вызовы `IUnknown::AddRef` на инкапсулированный указатель на интерфейс, вызов `E_POINTER` ошибка, если указатель имеет значение NULL.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)