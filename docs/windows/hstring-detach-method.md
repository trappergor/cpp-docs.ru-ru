---
title: Метод HString::Detach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::Detach
dev_langs:
- C++
ms.assetid: 5006ee13-549d-40a8-8dfe-d3fb3b5e18b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bfd4390cdc786836b08e77b4ee699e44cc42618
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569730"
---
# <a name="hstringdetach-method"></a>Метод HString::Detach
Отменяет связывание заданных **HString** объект с его базовым значением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HSTRING Detach() throw()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Базовый **HString** значение до запуска операции отсоединения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)