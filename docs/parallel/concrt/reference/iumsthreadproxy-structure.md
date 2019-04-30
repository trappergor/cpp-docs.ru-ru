---
title: Структура IUMSThreadProxy
ms.date: 11/04/2016
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
ms.openlocfilehash: 258f249aa178b73da2080cca888409dc07f63dbb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345517"
---
# <a name="iumsthreadproxy-structure"></a>Структура IUMSThreadProxy

Абстракция для потока выполнения. Если требуется предоставлять для планировщика потоки планировщика в пользовательском режиме (UMS), задайте для элемента политики планировщика `SchedulerKind` значение `UmsThreadDefault` и реализуйте интерфейс `IUMSScheduler`. Потоки UMS поддерживаются только в 64-разрядных операционных системах Windows 7 и более поздних версий.

## <a name="syntax"></a>Синтаксис

```
struct IUMSThreadProxy : public IThreadProxy;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IUMSThreadProxy::EnterCriticalRegion](#entercriticalregion)|Вызывается для ввода критической области. При использовании внутри критической области, планировщик не будет наблюдать асинхронные операции блокирования, происходящие во время области. Это означает, что планировщик не будет введен к снова для ошибок страниц, приостановки потока, вызовов асинхронных процедур ядра (APC) и т. д., для потока UMS.|
|[IUMSThreadProxy::EnterHyperCriticalRegion](#enterhypercriticalregion)|Вызывается для ввода hyper критической области. При использовании внутри hyper критической области, планировщик не будет наблюдать любые блокирующие операции, которые происходят во время области. Это означает, что в планировщик не будет повторных входов для блокирующих вызовов функции, блокирующих попыток получения блокировки, сбоев страниц, приостановок потока, вызовов асинхронных процедур ядра (APC) и т. п. для потока UMS.|
|[IUMSThreadProxy::ExitCriticalRegion](#exitcriticalregion)|Вызывается для выхода из критической области.|
|[IUMSThreadProxy::ExitHyperCriticalRegion](#exithypercriticalregion)|Вызывается для выхода из hyper критической области.|
|[IUMSThreadProxy::GetCriticalRegionType](#getcriticalregiontype)|Возвращает тип критической области, прокси-поток находится в пределах. Поскольку hyper критических областей являются подмножеством для критических областей, если введен код критической области, а затем hyper критической области, `InsideHyperCriticalRegion` будут возвращены.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[IThreadProxy](ithreadproxy-structure.md)

`IUMSThreadProxy`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

##  <a name="entercriticalregion"></a>  Метод IUMSThreadProxy::EnterCriticalRegion

Вызывается для ввода критической области. При использовании внутри критической области, планировщик не будет наблюдать асинхронные операции блокирования, происходящие во время области. Это означает, что планировщик не будет введен к снова для ошибок страниц, приостановки потока, вызовов асинхронных процедур ядра (APC) и т. д., для потока UMS.

```
virtual int EnterCriticalRegion() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Новая глубина критической области. Критические области являются реентерабельным.

##  <a name="enterhypercriticalregion"></a>  Метод IUMSThreadProxy::EnterHyperCriticalRegion

Вызывается для ввода hyper критической области. При использовании внутри hyper критической области, планировщик не будет наблюдать любые блокирующие операции, которые происходят во время области. Это означает, что в планировщик не будет повторных входов для блокирующих вызовов функции, блокирующих попыток получения блокировки, сбоев страниц, приостановок потока, вызовов асинхронных процедур ядра (APC) и т. п. для потока UMS.

```
virtual int EnterHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Новая глубина hyper критической области. Hyper критические области являются реентерабельным.

### <a name="remarks"></a>Примечания

Планировщик должен быть чрезвычайно осторожным, что методы, которые она вызывает, и что блокирует его, получает в таких регионах. Если код в такой области блокирует блокировку, которая удерживается каким-то, что планировщик отвечает за планирование, может возникнуть взаимоблокировка.

##  <a name="exitcriticalregion"></a>  Метод IUMSThreadProxy::ExitCriticalRegion

Вызывается для выхода из критической области.

```
virtual int ExitCriticalRegion() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Новая глубина критической области. Критические области являются реентерабельным.

##  <a name="exithypercriticalregion"></a>  Метод IUMSThreadProxy::ExitHyperCriticalRegion

Вызывается для выхода из hyper критической области.

```
virtual int ExitHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Новая глубина hyper критической области. Hyper критические области являются реентерабельным.

##  <a name="getcriticalregiontype"></a>  Метод IUMSThreadProxy::GetCriticalRegionType

Возвращает тип критической области, прокси-поток находится в пределах. Поскольку hyper критических областей являются подмножеством для критических областей, если введен код критической области, а затем hyper критической области, `InsideHyperCriticalRegion` будут возвращены.

```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Тип критической области прокси-поток находится в пределах.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IUMSScheduler](iumsscheduler-structure.md)
