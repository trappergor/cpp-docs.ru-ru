---
title: Класс CComSimpleThreadAllocator | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1538d5148eeb1eb95c51150a43ef5dd7b107cae3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033554"
---
# <a name="ccomsimplethreadallocator-class"></a>Класс CComSimpleThreadAllocator

Этот класс управляет выделения потока для класса `CComAutoThreadModule`.

## <a name="syntax"></a>Синтаксис

```
class CComSimpleThreadAllocator
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComSimpleThreadAllocator::GetThread](#getthread)|Выбирает поток.|

## <a name="remarks"></a>Примечания

`CComSimpleThreadAllocator` Управляет Выбор потоков для [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread` просто выполняет циклический переход по каждому потоку и возвращает следующим в последовательности.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="getthread"></a>  CComSimpleThreadAllocator::GetThread

Выбирает поток, указав следующий поток в последовательности.

```
int GetThread(CComApartment* /* pApt */, int nThreads);
```

### <a name="parameters"></a>Параметры

*pApt*<br/>
Не используется в реализации библиотеки ATL по умолчанию.

*nThreads*<br/>
Максимальное число потоков в модуле exe-файла.

### <a name="return-value"></a>Возвращаемое значение

Целое число от нуля и (*nThreads* - 1). Определяет один из потоков в модуле exe-файла.

### <a name="remarks"></a>Примечания

Можно переопределить `GetThread` предоставить другой метод выделения или сделать использование *pApt* параметра.

`GetThread` вызывается [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).

## <a name="see-also"></a>См. также

[Класс CComApartment](../../atl/reference/ccomapartment-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
