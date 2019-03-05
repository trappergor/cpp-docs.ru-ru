---
title: Класс CInternetException
ms.date: 11/04/2016
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
ms.openlocfilehash: dedf8926f02dd36dc8d6ac8ab5ff4056b60dfc91
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270268"
---
# <a name="cinternetexception-class"></a>Класс CInternetException

Представляет условие исключения, касающееся интернет-операции.

## <a name="syntax"></a>Синтаксис

```
class CInternetException : public CException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CInternetException::CInternetException](#cinternetexception)|Создает объект `CInternetException`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CInternetException::m_dwContext](#m_dwcontext)|Значение контекста, связанные с операцией, которая вызвала исключение.|
|[CInternetException::m_dwError](#m_dwerror)|Ошибки, вызвавшей исключение.|

## <a name="remarks"></a>Примечания

`CInternetException` Класс включает две открытые члены данных: один содержит код ошибки, связанное с исключением, а другое содержит идентификатор контекста для Интернет-приложения, с которым связана ошибка.

Дополнительные сведения об идентификаторах контекста для веб-приложений см. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

##  <a name="cinternetexception"></a>  CInternetException::CInternetException

Эта функция-член вызывается, когда `CInternetException` создается объект.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>Параметры

*dwError*<br/>
Ошибки, вызвавшей исключение.

### <a name="remarks"></a>Примечания

Чтобы создать CInternetException, вызовите глобальную функцию MFC [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).

##  <a name="m_dwcontext"></a>  CInternetException::m_dwContext

Контекст значение, связанное с соответствующим Интернет-операции.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>Примечания

Идентификатор контекста изначально указывается в [CInternetSession](../../mfc/reference/cinternetsession-class.md) и передаются по MFC для [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- и [CInternetFile](../../mfc/reference/cinternetfile-class.md)-производные классы. Можно переопределить поведение по умолчанию и назначить любой *dwContext* параметр значение по своему выбору. *dwContext* связан с любой операции данного объекта. *dwContext* определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).

##  <a name="m_dwerror"></a>  CInternetException::m_dwError

Ошибки, вызвавшей исключение.

```
DWORD m_dwError;
```

### <a name="remarks"></a>Примечания

Значение этой ошибки может стать системой код ошибки, в WINERROR. H, или значение ошибки из WININET. З.

Список кодов ошибок Win32, см. в разделе [коды ошибок](/windows/desktop/Debug/system-error-codes). Список сообщений об ошибках конкретного Интернет см. в разделе. Оба раздела, в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)
