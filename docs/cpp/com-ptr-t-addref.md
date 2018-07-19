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
ms.openlocfilehash: 40ed48b54a3862f7ac5804e7652d98b661bb071d
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940996"
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef
**Блок, относящийся только к системам Microsoft**  
  
 Вызовы `AddRef` функцию-член `IUnknown` на инкапсулированный указатель на интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
void AddRef( );  
  
```  
  
## <a name="remarks"></a>Примечания  
 Вызовы `IUnknown::AddRef` на инкапсулированный указатель на интерфейс, вызывает ошибку E_POINTER, если указатель имеет значение NULL.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)