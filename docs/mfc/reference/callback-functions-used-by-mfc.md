---
title: Функции обратного вызова, используемые MFC
ms.date: 11/04/2016
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: 8d84f939795e768c6b1356dcd8dc291421aedfdc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371140"
---
# <a name="callback-functions-used-by-mfc"></a>Функции обратного вызова, используемые MFC

Три функции обратного вызова отображаются в библиотеке класса Microsoft Foundation. Эти функции обратного вызова передаются [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring), и [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc). Обратите внимание, что все функции обратного вызова должны заманивать исключения MFC перед возвращением в Windows, так как исключения не могут быть брошены через границы обратного вызова. Для получения дополнительной информации об [Exceptions](../../mfc/exception-handling-in-mfc.md)исключениях см.

|Имя||
|----------|-----------------|
|[Функция обратного вызова для CDC::EnumObjects](#enum_objects)||
|[Функция обратного вызова для CDC::GrayString](#graystring)||
|[Функция обратного вызова для CDC::SetAbortProc](#setabortproc)||

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="callback-function-for-cdcenumobjects"></a><a name="enum_objects"></a>Функция обратного вызова для CDC::EnumObjects

Название *ObjectFunc* является заполнителем для функции, поставляемой приложением.

### <a name="syntax"></a>Синтаксис

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>Параметры

*lpszLogObject*<br/>
Указывает на структуру данных [LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen) или [LOGBRUSH,](/windows/win32/api/wingdi/ns-wingdi-logbrush) содержащую информацию о логических атрибутах объекта.

*lpData*<br/>
Указывает на данные, предоставленные `EnumObjects` приложением, передаваемые функции.

### <a name="return-value"></a>Возвращаемое значение

Функция обратного вызова возвращает **Int**. Значение этого возврата определяется пользователем. Если функция обратного вызова `EnumObjects` возвращается 0, останавливается перечисление рано.

### <a name="remarks"></a>Remarks

Фактическое имя должно быть экспортировано.

## <a name="callback-function-for-cdcgraystring"></a><a name="graystring"></a>Функция обратного вызова для CDC::GrayString

*OutputFunc* является заполнителем для приложения, поставляемого вызова функции вызова имя.

### <a name="syntax"></a>Синтаксис

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>Параметры

*Hdc*<br/>
Определяет контекст устройства памяти с битовой картой, по `nWidth` `nHeight` крайней мере, ширины и высоты, указанной и к `GrayString`.

*lpData*<br/>
Указывает на строку символов, которую необходимо нарисовать.

*Ncount*<br/>
Определяет количество символов для вывода.

### <a name="return-value"></a>Возвращаемое значение

Значение возврата функции обратного вызова должно быть правдой, чтобы указать на успех; в противном случае это FALSE.

### <a name="remarks"></a>Remarks

Функция обратного вызова *(OutputFunc*) должна нарисовать изображение относительно координат (0,0), а не *(x*, *y).*

## <a name="callback-function-for-cdcsetabortproc"></a><a name="setabortproc"></a>Функция обратного вызова для CDC::SetAbortProc

Название *AbortFunc* является заполнителем для приложения, поставляемого название функции.

### <a name="syntax"></a>Синтаксис

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>Параметры

*Hpr*<br/>
Идентифицирует контекст устройства.

*Код*<br/>
Указывается, произошла ли ошибка. Это 0, если ошибки не произошло. Это SP_OUTOFDISK, если менеджер печати в настоящее время из дискового пространства и больше диска пространство станет доступным, если приложение ждет. Если *код* SP_OUTOFDISK, приложение не должно прерывать работу печати. Если это не так, он должен уступить `PeekMessage` `GetMessage` менеджеру печати, позвонив в функцию или функцию Windows.

### <a name="return-value"></a>Возвращаемое значение

Значение возврата функции обработчика прерывания неявляется, если задание печати будет продолжено, и 0, если оно отменено.

### <a name="remarks"></a>Remarks

Фактическое название должно быть экспортировано, как описано в разделе Замечания [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc).

## <a name="see-also"></a>См. также раздел

[Структуры, стили, обратные вызовы и схемы сообщений](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC:EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)
