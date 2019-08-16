---
title: Класс Цинтернетексцептион
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
ms.openlocfilehash: c4f4c7a5b7594270aff9dfbc224e9a66ba09be3f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505911"
---
# <a name="cinternetexception-class"></a>Класс Цинтернетексцептион

Представляет условие исключения, касающееся интернет-операции.

## <a name="syntax"></a>Синтаксис

```
class CInternetException : public CException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Цинтернетексцептион:: Цинтернетексцептион](#cinternetexception)|Создает объект `CInternetException`.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Цинтернетексцептион:: m_dwContext](#m_dwcontext)|Значение контекста, связанное с операцией, вызвавшей исключение.|
|[Цинтернетексцептион:: m_dwError](#m_dwerror)|Ошибка, вызвавшая исключение.|

## <a name="remarks"></a>Примечания

`CInternetException` Класс включает два открытых члена данных: один содержит код ошибки, связанный с исключением, а другой — идентификатор контекста Интернет приложения, связанного с ошибкой.

Дополнительные сведения об идентификаторах контекста для Интернет приложений см. в статье [Интернет – программирование с помощью WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>Требования

**Заголовок:** афксинет. h

##  <a name="cinternetexception"></a>Цинтернетексцептион:: Цинтернетексцептион

Эта функция-член вызывается при `CInternetException` создании объекта.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>Параметры

*дверрор*<br/>
Ошибка, вызвавшая исключение.

### <a name="remarks"></a>Примечания

Чтобы создать исключение Цинтернетексцептион, вызовите глобальную функцию MFC [афкссровинтернетексцептион](internet-url-parsing-globals.md#afxthrowinternetexception).

##  <a name="m_dwcontext"></a>Цинтернетексцептион:: m_dwContext

Значение контекста, связанное с операцией, связанной с Интернетом.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>Примечания

Идентификатор контекста изначально указывается в [Цинтернетсессион](../../mfc/reference/cinternetsession-class.md) и передается из MFC в классы, производные от [Цинтернетконнектион](../../mfc/reference/cinternetconnection-class.md)и [Цинтернетфиле](../../mfc/reference/cinternetfile-class.md). Вы можете переопределить это значение по умолчанию и назначить любой параметр *двконтекст* со значением по своему усмотрению. *двконтекст* связан с любой операцией данного объекта. *двконтекст* определяет сведения о состоянии операции, возвращаемые [Цинтернетсессион:: онстатускаллбакк](../../mfc/reference/cinternetsession-class.md#onstatuscallback).

##  <a name="m_dwerror"></a>Цинтернетексцептион:: m_dwError

Ошибка, вызвавшая исключение.

```
DWORD m_dwError;
```

### <a name="remarks"></a>Примечания

Это значение ошибки может быть кодом системной ошибки, который находится в файле WINERROR. H или значение ошибки из WININET. Высоты.

Список кодов ошибок Win32 см. в разделе [коды ошибок](/windows/win32/Debug/system-error-codes). Список сообщений об ошибках, связанных с Интернетом, см. в разделе. Оба раздела находятся в Windows SDK.

## <a name="see-also"></a>См. также

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)
