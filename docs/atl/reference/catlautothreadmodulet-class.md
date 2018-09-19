---
title: Класс CAtlAutoThreadModuleT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46198390ce25cb655b94c0ca4769321fc3e9362d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099711"
---
# <a name="catlautothreadmodulet-class"></a>Класс CAtlAutoThreadModuleT

Этот класс предоставляет методы для реализации пула потоков, модель с подразделением COM-сервера.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T,
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, который реализует COM-сервера.

*ThreadAllocator*<br/>
Класс управления выбора потоков. Значение по умолчанию — [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).

*dwWait*<br/>
Интервал времени ожидания в миллисекундах. Значение по умолчанию равно INFINITE, что означает интервал времени ожидания для метода, никогда не истекает.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|Эта статическая функция динамически вычисляет и возвращает максимальное число потоков для модуля exe-файла, в зависимости от количества процессоров.|

## <a name="remarks"></a>Примечания

Класс [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) является производным от `CAtlAutoThreadModuleT` для реализации пула потоков, модель с подразделением COM-сервера. Он заменяет устаревший класс [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

> [!NOTE]
>  Этот класс не следует в библиотеке DLL, по умолчанию *dwWait* значение INFINITE будет привести к взаимоблокировке при выгрузке библиотеки DLL.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlAutoThreadModule`

`CAtlAutoThreadModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="getdefaultthreads"></a>  CAtlAutoThreadModuleT::GetDefaultThreads

Эта статическая функция динамически вычисляет и возвращает максимальное число потоков для модуля exe-файла, в зависимости от количества процессоров.

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Возвращаемое значение

Число потоков, создаваемых в модуле exe-файла.

### <a name="remarks"></a>Примечания

Переопределите этот метод, если вы хотите использовать другой метод для вычисления число потоков. По умолчанию число потоков зависит от количества процессоров.

## <a name="see-also"></a>См. также

[Класс IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Класс IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Модульные классы](../../atl/atl-module-classes.md)
