---
title: Класс DeferrableEventArgs | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::DeferrableEventArgs
- event/Microsoft::WRL::DeferrableEventArgs::GetDeferral
- event/Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::DeferrableEventArgs class
- Microsoft::WRL::DeferrableEventArgs::GetDeferral method
- Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished method
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 082cae10bbd01c4c46fcfaa84bfd94ba6178bc1a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401788"
---
# <a name="deferrableeventargs-class"></a>Класс DeferrableEventArgs

Класс шаблона, используемый для типов аргументов событий для задержек.

## <a name="syntax"></a>Синтаксис

```cpp
template <
typename TEventArgsInterface,
typename TEventArgsClass
>
class DeferrableEventArgs : public TEventArgsInterface
```

### <a name="parameters"></a>Параметры

*TEventArgsInterface*<br/>
Тип интерфейса, который объявляет аргументы для отложенного события.

*TEventArgsClass*<br/>
Класс, реализующий *TEventArgsInterface*.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

Имя                                                         | Описание
------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------
[DeferrableEventArgs::GetDeferral](#getdeferral)             | Получает ссылку на [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объект, который представляет отложенное событие.
[DeferrableEventArgs::InvokeAllFinished](#invokeallfinished) | Вызывается, чтобы указать, что вся обработка для отложенного события завершена.

## <a name="remarks"></a>Примечания

Экземпляры этого класса передаются в обработчики событий для отложенных событий. Параметры шаблона представляют интерфейс, определяющий подробные сведения об аргументах событий для конкретного типа отложенного события, а также класс, реализующий этот интерфейс.

Класс отображается как первый аргумент обработчика событий для отложенного события. Можно вызвать [задержка](#getdeferral) метод для получения [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объект, из которого можно получить все сведения об отложенном событии. После завершения обработки событий необходимо вызвать завершение в объекте «Задержка». Затем следует вызвать [InvokeAllFinished](#invokeallfinished) в конце метода обработчика событий, который гарантирует, что завершение всех отложенных событий передается надлежащим образом.

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::WRL

## <a name="getdeferral"></a>DeferrableEventArgs::GetDeferral

Получает ссылку на [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объект, который представляет отложенное событие.

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```

### <a name="parameters"></a>Параметры

*результат*<br/>
Указатель, который будет ссылаться на [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объекта после завершения вызова.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="invokeallfinished"></a>DeferrableEventArgs::InvokeAllFinished

Вызывается, чтобы указать, что вся обработка для отложенного события завершена.
  
```cpp
void InvokeAllFinished()  
```
  
### <a name="remarks"></a>Примечания

Этот метод следует вызывать после источник события вызовет [InvokeAll](../windows/eventsource-invokeall-method.md). Вызов этого метода предотвращает ввод последующих задержек и вызывает принудительное выполнение обработчика завершения, если задержки отсутствовали.
