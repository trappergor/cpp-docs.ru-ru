---
title: "Метод RuntimeClass::GetRuntimeClassName | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
dev_langs: C++
helpviewer_keywords: GetRuntimeClassName method
ms.assetid: f6388163-fe65-4948-a4bc-ae6826f480e7
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9987c539bb67e3989af851c3e4088e25b67f9136
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassgetruntimeclassname-method"></a>Метод RuntimeClass::GetRuntimeClassName

Возвращает имя класса среды выполнения текущего объекта RuntimeClass.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>Параметры

*runtimeName*  
После завершения операции представляет имя класса среды выполнения.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="remarks"></a>Примечания

Ошибка assert, если порожденный &#95; &#95; WRL_STRICT &#95; &#95; или &#95; &#95; WRL_FORCE_INSPECTABLE_CLASS_MACRO &#95; &#95; не определен.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс RuntimeClass](../windows/runtimeclass-class.md)