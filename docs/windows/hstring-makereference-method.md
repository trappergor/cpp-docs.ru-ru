---
title: Метод HString::MakeReference | Документы Microsoft
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
ms.openlocfilehash: e30b3ea3c6b791eb654a6fbbe91b3c87353f31c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882645"
---
# <a name="hstringmakereference-method"></a>Метод HString::MakeReference
Создает объект HStringReference из указанного строкового параметра.  
  
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
  
#### <a name="parameters"></a>Параметры  
 `sizeDest`  
 Параметр шаблона, задающее размер буфера назначения HStringReference.  
  
 `str`  
 Ссылка на строку расширенных символов.  
  
 `len`  
 Максимальная длина `str` буфером параметров для использования в этой операции. Если `len` параметр не указан, вся `str` параметр используется.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект HStringReference, значение которого совпадает со значением указанного `str` параметра.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)