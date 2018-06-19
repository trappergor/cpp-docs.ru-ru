---
title: Конструктор HString::HString | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs:
- C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a3188e137d3a39fb26ca4151f72073306038e46f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876882"
---
# <a name="hstringhstring-constructor"></a>Конструктор HString::HString
Инициализирует новый экземпляр класса HString.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HString(HSTRING hstr = nullptr) throw();  
HString(HString&& other) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `hstr`  
 Дескриптор HSTRING.  
  
 `other`  
 Существующий объект HString.  
  
## <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует новый объект HString, который является пустым.  
  
 Второй конструктор инициализирует новый объект HString значение существующего `other` параметра, а затем удаляет `other` параметра.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)