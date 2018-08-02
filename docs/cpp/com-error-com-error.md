---
title: _com_error::_com_error | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1389635c3ef026e8b3a7dfe13976cca58a15a82
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406722"
---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Блок, относящийся только к системам Microsoft**  
  
 Создает **_com_error** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false) throw( );  

_com_error( const _com_error& that ) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 *hr*  
 Информация HRESULT.  
  
 *perrinfo*  
 Объект `IErrorInfo`.  
  
 `bool fAddRef=false`  
 Дает конструктору указание вызвать метод AddRef на отличный от null `IErrorInfo` интерфейс. Это обеспечивает правильный подсчет ссылок в общем случае, когда владение интерфейсом передается в **_com_error** объект, например:  
  
```cpp 
throw _com_error(hr, perrinfo);  
```  
  
 Если вы не хотите код, чтобы передать права владения для **_com_error** объекта и `AddRef` необходим для смещения `Release` в **_com_error** деструктор, конструируется объект как выглядит следующим образом:  
  
```cpp 
_com_error err(hr, perrinfo, true);  
```  
  
 *,*  
 Существующий **_com_error** объекта.  
  
## <a name="remarks"></a>Примечания  
 Первый конструктор создает новый объект по заданному HRESULT и необязательный `IErrorInfo` объекта. Второй создает копию существующего **_com_error** объекта.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)