---
title: _com_ptr_t::QueryInterface | Документация Майкрософт
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
ms.openlocfilehash: 20d22fac89b151a28e856ac4eaf61021faa6bfd5
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407436"
---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface
**Блок, относящийся только к системам Microsoft**  
  
 Вызовы **QueryInterface** функцию-член `IUnknown` на инкапсулированный указатель на интерфейс.  
  
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
 *IID*  
 `IID` из указателя на интерфейс.  
  
 *p*  
 Необработанный указатель на интерфейс.  
  
## <a name="remarks"></a>Примечания  
 Вызовы `IUnknown::QueryInterface` на инкапсулированный указатель на интерфейс с указанным `IID` и возвращает результирующее необработанный указатель на интерфейс в *p*. Эта процедура возвращает значение HRESULT, указывающее успех или неудачу.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)