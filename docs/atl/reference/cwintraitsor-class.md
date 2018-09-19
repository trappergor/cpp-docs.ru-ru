---
title: Класс CWinTraitsOR | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48303c6115ac1d2314e3038556b8f98330a6182e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062674"
---
# <a name="cwintraitsor-class"></a>Класс CWinTraitsOR

Этот класс предоставляет метод для стандартизации стилей, которые используются при создании объекта окна.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0, 
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```

#### <a name="parameters"></a>Параметры

*t_dwStyle*<br/>
Стили окна по умолчанию.

*t_dwExStyle*<br/>
По умолчанию расширенные стили окна.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|Извлекает расширенные стили для `CWinTraitsOR` объекта.|
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|Извлекает стандартный стили `CWinTraitsOR` объекта.|

## <a name="remarks"></a>Примечания

Это [характеристиках окна](../../atl/understanding-window-traits.md) класс предоставляет простой метод стандартизации стилей, которые используются для создания объекта ATL окна. Использование специализации этого класса в качестве параметра шаблона для [CWindowImpl](../../atl/reference/cwindowimpl-class.md) или иной классы окон ATL чтобы указать минимальный набор стандартные и расширенные стили для использования экземпляров этого класса окна.

Используйте этот шаблон является специализацией в том случае, если вы хотите убедиться, что некоторые стили задано для всех экземпляров класса окна одновременно разрешая другие стили быть заданы для каждого экземпляра в вызове [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create).

Если вы хотите предоставить значение по умолчанию стили окна, которые будут использоваться только в том случае, когда другие стили не указаны в вызове `CWindowImpl::Create`, использовать [CWinTraits](../../atl/reference/cwintraits-class.md) вместо этого.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="getwndstyle"></a>  CWinTraitsOR::GetWndStyle

Вызывайте эту функцию для извлечения сочетания стандартных стилей (с помощью оператора логического или) `CWinTraits` объекта и стили по умолчанию, определяемое *t_dwStyle*.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Стили, используемые для создания окна.

### <a name="return-value"></a>Возвращаемое значение

Сочетание стили, которые передаются в *dwStyle* и объекты, заданные по умолчанию `t_dwStyle`, с помощью оператора логического или.

##  <a name="getwndexstyle"></a>  CWinTraitsOR::GetWndExStyle

Вызывайте эту функцию для извлечения сочетания (с помощью оператора логического или) расширенных стилей `CWinTraits` объекта и стили по умолчанию, определяемое `t_dwStyle`.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Параметры

*dwExStyle*<br/>
Расширенные стили, используемые для создания окна.

### <a name="return-value"></a>Возвращаемое значение

Сочетание расширенные стили, которые передаются в *dwExStyle* и по умолчанию, указанных по `t_dwExStyle`, с помощью оператора логического или

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Основные сведения о характеристиках окна](../../atl/understanding-window-traits.md)

