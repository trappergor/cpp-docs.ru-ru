---
title: _com_ptr_t::QueryInterface | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c046f1b1d14b7e7dbd44ca9f5f012e632efef6e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface
**Блок, относящийся только к системам Microsoft**  
  
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