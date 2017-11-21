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
ms.openlocfilehash: c82a3ae65ae65dfe43cb0ed645f802161f7a17f6
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
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