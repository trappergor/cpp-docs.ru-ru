---
title: "_com_ptr_t::QueryInterface | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs: C++
helpviewer_keywords: QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1dd546da4730bfd2995b4d97be8017807d2ae161
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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