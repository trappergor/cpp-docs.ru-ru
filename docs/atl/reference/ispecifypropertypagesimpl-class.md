---
title: Класс ИспеЦифипропертипажесимпл
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
ms.openlocfilehash: c201cf6d9d89ab1a6a8e888deee1be79e5770490
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495412"
---
# <a name="ispecifypropertypagesimpl-class"></a>Класс ИспеЦифипропертипажесимпл

Этот класс реализует `IUnknown` интерфейс [испеЦифипропертипажес](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) и предоставляет реализацию по умолчанию.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `ISpecifyPropertyPagesImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[ИспеЦифипропертипажесимпл::-выстр.](#getpages)|Заполняет считанный массив значений UUID. Каждый UUID соответствует CLSID для одной из страниц свойств, которые могут отображаться на странице свойств объекта.|

## <a name="remarks"></a>Примечания

Интерфейс [испеЦифипропертипажес](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) позволяет клиенту получить список идентификаторов CLSID для страниц свойств, поддерживаемых объектом. Класс `ISpecifyPropertyPagesImpl` предоставляет реализацию этого интерфейса по умолчанию и реализует `IUnknown` , отправляя сведения в устройство дампа в отладочных сборках.

> [!NOTE]
>  Не предоставляйте интерфейс, `ISpecifyPropertyPages` если объект не поддерживает страницы свойств.

**Связанные статьи** [Учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="getpages"></a>ИспеЦифипропертипажесимпл::-выстр.

Заполняет массив в структуре [КАУУИД](/windows/win32/api/ocidl/ns-ocidl-cauuid) идентификаторами CLSID для страниц свойств, которые могут отображаться на странице свойств объекта.

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>Примечания

ATL использует карту свойств объекта для получения каждого идентификатора CLSID.

См. раздел [испеЦифипропертипажес::-Pages](/windows/win32/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)<br/>
[Класс IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
