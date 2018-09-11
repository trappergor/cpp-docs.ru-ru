---
title: Метод SimpleClassFactory::CreateInstance | Документация Майкрософт
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
ms.openlocfilehash: d9dfb783a8e002f249d5f6b4cc0a45193669efb3
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603117"
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
Должно быть **nullptr**; в противном случае возвращается значение class_e_noaggregation.

SimpleClassFactory не поддерживает агрегирование. Если поддерживается агрегирование и создаваемый объект был частью агрегата, *pUnkOuter* должен быть указателем на управляющий `IUnknown` интерфейс агрегатной функции.

*riid*  
Идентификатор интерфейса объекта, который требуется создать.

*ppvObject*  
После завершения операции, указатель на экземпляр объекта, заданного параметром *riid* параметра.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="remarks"></a>Примечания

Если `__WRL_STRICT__` будет определен, Ошибка утверждения создается, если базовый класс, указанный в параметре шаблона класса не является производным от [RuntimeClass](../windows/runtimeclass-class.md), или не настроен со значением ClassicCom или WinRtClassicComMix [ RuntimeClassType](../windows/runtimeclasstype-enumeration.md) значение перечисления.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс SimpleClassFactory](../windows/simpleclassfactory-class.md)