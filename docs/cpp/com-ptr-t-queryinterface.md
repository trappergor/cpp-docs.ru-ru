---
title: "_com_ptr_t::QueryInterface | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
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
ms.openlocfilehash: 6b5c8fb9ca1d628b178c19b677b90f17cc992373
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface
**Блок, относящийся только к системам Майкрософт**  
  
 Вызовы `QueryInterface` функцию-член **IUnknown** на инкапсулированный указатель на интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType*& p   
) throw ( );  
template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType** p  
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `iid`  
 **IID** указателя на интерфейс.  
  
 `p`  
 Необработанный указатель на интерфейс.  
  
## <a name="remarks"></a>Примечания  
 Вызовы **IUnknown::QueryInterface** на инкапсулированный указатель на интерфейс с заданным **IID** и возвращает результирующее необработанный указатель на интерфейс в `p`. Эта процедура возвращает значение `HRESULT`, которое указывает успешность или сбой выполнения.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
