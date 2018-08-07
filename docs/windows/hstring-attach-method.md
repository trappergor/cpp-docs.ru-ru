---
title: Метод HString::Attach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::Attach
dev_langs:
- C++
ms.assetid: 69451979-0014-4959-bc5c-1e4ab6fb28e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 20a05bf603b874d260c95c010e6f0e8312b35649
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570993"
---
# <a name="hstringattach-method"></a>Метод HString::Attach
Связывает указанный **HString** объект с текущим **HString** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void Attach(  
       HSTRING hstr  
       ) throw()  
```  
  
#### <a name="parameters"></a>Параметры  
 *HSTR*  
 Существующий **HString** объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)