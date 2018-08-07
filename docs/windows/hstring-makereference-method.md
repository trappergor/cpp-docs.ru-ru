---
title: Метод HString::MakeReference | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
dev_langs:
- C++
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 673d5b10706580303f179ee453495b581d96eda3
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608339"
---
# <a name="hstringmakereference-method"></a>Метод HString::MakeReference
Создает `HStringReference` объект из указанного строкового параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[ sizeDest]);  
  
    template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[sizeDest],   
              unsigned int len);  
```  
  
### <a name="parameters"></a>Параметры  
 *sizeDest*  
 Параметр шаблона, который указывает размер целевой `HStringReference` буфера.  
  
 *str*  
 Ссылка на строку расширенных символов.  
  
 *функция Len*  
 Максимальная длина *str* буфером параметров для использования в данной операции. Если *len* параметр не указан, весь *str* используется параметр.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `HStringReference` Объект, значение которого совпадает со значением указанного *str* параметра.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)