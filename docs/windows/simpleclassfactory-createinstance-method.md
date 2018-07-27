---
title: Метод SimpleClassFactory::CreateInstance | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a31d364a6464962b8243cfaced03131a20f9324
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892752"
---
# <a name="simpleclassfactorycreateinstance-method"></a>Метод SimpleClassFactory::CreateInstance

Создает экземпляр указанного интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

### <a name="parameters"></a>Параметры

*pUnkOuter*  
Должно быть `nullptr`; в противном случае возвращается значение CLASS_E_NOAGGREGATION.

SimpleClassFactory не поддерживает агрегирование. Если поддерживается агрегирование и создаваемый объект был частью агрегата, `pUnkOuter` будет указателем на управляющий интерфейс агрегата IUnknown.

*riid*  
Идентификатор интерфейса объекта, который требуется создать.

*ppvObject*  
После завершения операции представляет указатель на экземпляр объекта, который задается параметром `riid`.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="remarks"></a>Примечания

Если &#95; &#95;WRL_STRICT&#95; &#95; будет определено, Ошибка утверждения создается, если базовый класс, указанный в параметре шаблона класса не является производным от [RuntimeClass](../windows/runtimeclass-class.md), или не настроен со значением ClassicCom или WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) значение перечисления.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс SimpleClassFactory](../windows/simpleclassfactory-class.md)