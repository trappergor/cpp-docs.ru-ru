---
title: "Конструктор HString::HString | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs: C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d13f532484cc071744b9b823546052d92c6f6b78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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