---
title: "_com_error::_com_error | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::_com_error
dev_langs: C++
helpviewer_keywords: _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: df04357afd35b546fb43c90a102b7dc0cacdc95e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Блок, относящийся только к системам Microsoft**  
  
 Создает объект `_com_error`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      _com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false  
) throw( );  
_com_error(  
   const _com_error& that   
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `hr`  
 Информация о значении `HRESULT`.  
  
 `perrinfo`  
 **IErrorInfo** объекта.  
  
 **bool fAddRef = false**  
 Дает конструктору указание вызвать метод AddRef на ненулевое значение **IErrorInfo** интерфейса. Это обеспечивает правильный подсчет ссылок в распространенной ситуации, когда право владения интерфейсом передается в объект `_com_error`, например:  
  
```  
throw _com_error(hr, perrinfo);  
```  
  
 Если не требуется, чтобы код передавал право владения `_com_error` объекта и `AddRef` необходим для смещения **выпуска** в `_com_error` деструктор, создавайте объект следующим образом:  
  
```  
_com_error err(hr, perrinfo, true);  
```  
  
 `that`  
 Существующий объект `_com_error`.  
  
## <a name="remarks"></a>Примечания  
 Первый конструктор создает новый объект по заданному `HRESULT` и необязательные **IErrorInfo** объекта. Второй создает копию существующего объекта `_com_error`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)