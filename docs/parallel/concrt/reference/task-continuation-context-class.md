---
title: Класс task_continuation_context | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_continuation_context
- PPLTASKS/concurrency::task_continuation_context
- PPLTASKS/concurrency::task_continuation_context::get_current_winrt_context
- PPLTASKS/concurrency::task_continuation_context::use_arbitrary
- PPLTASKS/concurrency::task_continuation_context::use_current
- PPLTASKS/concurrency::task_continuation_context::use_default
- PPLTASKS/concurrency::task_continuation_context::use_synchronous_execution
dev_langs:
- C++
helpviewer_keywords:
- task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0b1cff6dbb816d3dddc6b3ad8090fd30413e336
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392636"
---
# <a name="taskcontinuationcontext-class"></a>Класс task_continuation_context

Класс `task_continuation_context` позволяет указать место продолжения выполнения задачи. Ключ используется только для использования этого класса из приложения среды выполнения Windows. Для среды Windows выполнения приложений контекст выполнения продолжения задачи определяется средой выполнения и не настраивается.

## <a name="syntax"></a>Синтаксис

```
class task_continuation_context : public details::_ContextCallback;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[get_current_winrt_context](#get_current_winrt_context)|Возвращает объект контекста продолжения задачи, представляющий текущий контекст потока winrt.|
|[use_arbitrary](#use_arbitrary)|Создает контекст продолжения выполнения задачи, который позволяет среде выполнения возможность выбора контекста для продолжения.|
|[use_current](#use_current)|Возвращает объект контекста продолжения задачи, представляющий контекст текущего выполнения.|
|[use_default](#use_default)|Создает контекст продолжения задачи по умолчанию.|
|[use_synchronous_execution](#use_synchronous_execution)|Возвращает объект контекста продолжения задачи, представляющий контекст синхронного выполнения.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_ContextCallback`

`task_continuation_context`

## <a name="requirements"></a>Требования

**Заголовок:** ppltasks.h

**Пространство имен:** concurrency

## <a name="get_current_winrt_context"></a> get_current_winrt_context

Возвращает объект контекста продолжения задачи, представляющий текущий контекст потока WinRT.

## <a name="syntax"></a>Синтаксис

```
static task_continuation_context get_current_winrt_context();
```

## <a name="return-value"></a>Возвращаемое значение

Текущий контекст потока среды выполнения Windows. Возвращает пустой task_continuation_context при вызове из контекста выполнения, отличных от Windows.

## <a name="remarks"></a>Примечания

`get_current_winrt_context` Метод выполняет сбор контекста среды выполнения Windows вызывающего объекта потока. Он возвращает пустом контексте среды Windows выполнения вызывающим объектам.

Значение, возвращенное `get_current_winrt_context` позволяют среде выполнения понять, что продолжение должно выполняться в модели подразделения в захваченном контексте (STA или MTA), даже если предшествующая задача является с поддержкой. Задача — это задача, развертывающая среды выполнения Windows с поддержкой `IAsyncInfo` интерфейс или задача, наследуемая от такой задачи.

Этот метод аналогичен методу `use_current` метод, но она также доступна в машинный код C++ не используется C + +/ CX поддержка расширения. Он предназначен для использования Опытные пользователи написание C + +/ CX-независимый код библиотеки для машинного кода и вызывающие объекты среды выполнения Windows. Если данная функция необходима, мы не рекомендуем `use_current` метод, который доступен только для C + +/ CX клиентов.

##  <a name="use_arbitrary"></a> use_arbitrary

Создает контекст продолжения выполнения задачи, который позволяет среде выполнения возможность выбора контекста для продолжения.

```
static task_continuation_context use_arbitrary();
```

### <a name="return-value"></a>Возвращаемое значение

Контекст продолжения задачи, представляющий произвольное местоположение.

### <a name="remarks"></a>Примечания

Если используется этот контекст продолжения, продолжение выполняется в контексте, выбранном средой выполнения, даже если предшествующая задача поддерживает разделение.

`use_arbitrary` можно использовать, чтобы отключить поведение по умолчанию для продолжения учитывающей подразделения задачи созданной в STA.

Этот метод доступен только для приложений среды выполнения Windows.

##  <a name="use_current"></a> use_current

Возвращает объект контекста продолжения задачи, представляющий контекст текущего выполнения.

```
static task_continuation_context use_current();
```

### <a name="return-value"></a>Возвращаемое значение

Указывает текущий контекст выполнения.

### <a name="remarks"></a>Примечания

Этот метод выполняет сбор контекста среды выполнения Windows вызывающего объекта, чтобы продолжения могли выполняться в правильном подразделении.

Значение, возвращенное `use_current` позволяют среде выполнения понять, что продолжение должно выполняться в захваченном контексте (STA или MTA) независимо от того, является ли предшествующей задачи с поддержкой. Задача — это задача, развертывающая среды выполнения Windows с поддержкой `IAsyncInfo` интерфейс или задача, наследуемая от такой задачи.

Этот метод доступен только для приложений среды выполнения Windows.

##  <a name="use_default"></a> use_default

Создает контекст продолжения задачи по умолчанию.

```
static task_continuation_context use_default();
```

### <a name="return-value"></a>Возвращаемое значение

Контекст продолжения по умолчанию.

### <a name="remarks"></a>Примечания

Контекст по умолчанию используется в том случае, если не указан контекст продолжения при вызове `then` метод. В Windows приложений для Windows 7 и ниже, а также классических приложений на Windows 8 и более поздних версий среда выполнения определяет, где выполняются продолжения задачи. Тем не менее, в приложении среды выполнения Windows, контекст продолжения по умолчанию для продолжения учитывающей подразделения задачи является подразделением где `then` вызывается.

Задача — это задача, развертывающая среды выполнения Windows с поддержкой `IAsyncInfo` интерфейс или задача, наследуемая от такой задачи. Таким образом Если продолжение учитывающей подразделения задачи в STA среды выполнения Windows, продолжение будет выполняться в этом STA.

Продолжение учитывающей задачи не подразделениями будет выполняться в контексте, выбранном средой выполнения.

## <a name="use_synchronous_execution"></a> task_continuation_context::use_synchronous_execution

Возвращает объект контекста продолжения задачи, представляющий контекст синхронного выполнения.

## <a name="syntax"></a>Синтаксис

```
static task_continuation_context use_synchronous_execution();
```

## <a name="return-value"></a>Возвращаемое значение

Контекст выполнения синхронной.

## <a name="remarks"></a>Примечания

`use_synchronous_execution` Метод вынуждает для синхронного выполнения в контексте, причиной завершения предшествующей задачи задача продолжения.

Если предшествующая задача уже была завершена, при присоединении продолжение, продолжение выполняется синхронно в контекст, который присоединяет продолжение.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
