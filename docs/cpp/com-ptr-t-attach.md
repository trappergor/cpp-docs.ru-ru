---
title: "_com_ptr_t::Attach | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
caps.latest.revision: 6
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
ms.openlocfilehash: aa14a5fb0e54971e19de1b46317d768e7fc06a2e
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtattach"></a>_com_ptr_t::Attach
**Блок, относящийся только к системам Майкрософт**  
  
 Инкапсулирует необработанный указатель на интерфейс для типа этого интеллектуального указателя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      void Attach(  
   Interface* pInterface   
) throw( );  
void Attach(  
   Interface* pInterface,  
   bool fAddRef   
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `pInterface`  
 Необработанный указатель на интерфейс.  
  
 `fAddRef`  
 Если это **true**, затем `AddRef` вызывается. Если это **false**, `_com_ptr_t` принимает право на владение базовым указателем на интерфейс без вызова `AddRef`.  
  
## <a name="remarks"></a>Примечания  
  
-   **Присоединение (**`pInterface`**)** `AddRef` не вызывается.     Право на владение интерфейсом передается данному объекту `_com_ptr_t`. **Выпуск** вызывается для уменьшения числа ссылок для ранее инкапсулированного указателя.  
  
-   **Присоединение (** `pInterface` **,**`fAddRef`**)** Если `fAddRef` — **true**, `AddRef` вызывается для увеличения ссылки счетчик для указателя инкапсулированного интерфейса.       Если `fAddRef` — **false**, то `_com_ptr_t` принимает право на владение базовым указателем на интерфейс без вызова `AddRef`. **Выпуск** вызывается для уменьшения числа ссылок для ранее инкапсулированного указателя.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
