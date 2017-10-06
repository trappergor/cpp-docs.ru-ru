---
title: "_com_error::_com_error | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
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
ms.openlocfilehash: 81efabf796d8d596326629af999f1932501befb5
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Блок, относящийся только к системам Майкрософт**  
  
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
