---
title: Класс IProvideClassInfo2Impl
ms.date: 11/04/2016
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
ms.openlocfilehash: f0ff3607002d32b4e21f7fc2199cc5da3662af8b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495539"
---
# <a name="iprovideclassinfo2impl-class"></a>Класс IProvideClassInfo2Impl

Этот класс предоставляет реализацию методов [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) и [IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) по умолчанию.

## <a name="syntax"></a>Синтаксис

```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```

#### <a name="parameters"></a>Параметры

*пкоклсид*<br/>
Указатель на идентификатор coclass.

*псрЦид*<br/>
Указатель на идентификатор исходящего disp-интерфейса по умолчанию coclass.

*плибид*<br/>
Указатель на идентификатор LIBID библиотеки типов, который содержит сведения об интерфейсе. По умолчанию передается библиотека типов на уровне сервера.

*вмажор*<br/>
Основной номер версии для библиотеки типов. Значение по умолчанию — 1.

*вминор*<br/>
Дополнительный номер версии для библиотеки типов. Значение по умолчанию — 0.

*тихкласс*<br/>
Класс, используемый для управления информацией о типе coclass. Значение по умолчанию — `CComTypeInfoHolder`.

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|name|Описание|
|----------|-----------------|
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IProvideClassInfo2Impl:: Жетклассинфо](#getclassinfo)|`ITypeInfo` Извлекает указатель на сведения о типе coclass.|
|[IProvideClassInfo2Impl:: a GUID](#getguid)|Извлекает идентификатор GUID исходящего интерфейса пользователя объекта.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[IProvideClassInfo2Impl::_tih](#_tih)|Управляет сведениями о типе для компонентного класса.|

## <a name="remarks"></a>Примечания

Интерфейс [IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) расширяет `GetGUID` класс [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) , добавляя метод. Этот метод позволяет клиенту получить исходящий интерфейс IID объекта для набора событий по умолчанию. Класс `IProvideClassInfo2Impl` предоставляет реализацию `IProvideClassInfo` методов и `IProvideClassInfo2` по умолчанию.

`IProvideClassInfo2Impl`содержит статический член типа `CComTypeInfoHolder` , который управляет сведениями о типе для компонентного класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="getclassinfo"></a>IProvideClassInfo2Impl:: Жетклассинфо

`ITypeInfo` Извлекает указатель на сведения о типе coclass.

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Примечания

См. раздел [IProvideClassInfo:: жетклассинфо](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo) в Windows SDK.

##  <a name="getguid"></a>IProvideClassInfo2Impl:: a GUID

Извлекает идентификатор GUID исходящего интерфейса пользователя объекта.

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>Примечания

См. [IProvideClassInfo2:: a GUID](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid) в Windows SDK.

##  <a name="iprovideclassinfo2impl"></a>IProvideClassInfo2Impl::IProvideClassInfo2Impl

Конструктор.

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>Примечания

Вызывает `AddRef` для члена [_tih](#_tih) . Деструктор вызывает `Release`.

##  <a name="_tih"></a>IProvideClassInfo2Impl::_tih

Этот статический элемент данных является экземпляром параметра шаблона класса *тихкласс*, который по умолчанию имеет `CComTypeInfoHolder`значение.

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>Примечания

`_tih`управляет сведениями о типе для компонентного класса.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
