---
title: Функции обратного вызова, используемые MFC
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.functions
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: acb7b6c677d03ef1320e24373671a7577c2ccda8
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178438"
---
# <a name="callback-functions-used-by-mfc"></a>Функции обратного вызова, используемые MFC

Отобразятся три функции обратного вызова в библиотеке Microsoft Foundation Class. Эти функции обратного вызова передаются [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring), и [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc). Обратите внимание на то, что все функции обратного вызова должен перехват исключений MFC перед возвратом к Windows, так как исключения не может вызываться через границы обратного вызова. Дополнительные сведения об исключениях см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

|name||
|----------|-----------------|
|[Функция обратного вызова для CDC::EnumObjects](#enum_objects)||
|[Функция обратного вызова для CDC::GrayString](#graystring)||
|[Функция обратного вызова для CDC::SetAbortProc](#setabortproc)||

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="enum_objects"></a> Функция обратного вызова для CDC::EnumObjects

*ObjectFunc* имя — это имя функции, предоставляемую приложением.

### <a name="syntax"></a>Синтаксис

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>Параметры

*lpszLogObject*<br/>
Указывает на [LOGPEN](/windows/desktop/api/Wingdi/ns-wingdi-taglogpen) или [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) структура данных, которая содержит сведения о логических атрибутов объекта.

*lpData*<br/>
Указывает на данные, предоставляемую приложением, передаваемый `EnumObjects` функции.

### <a name="return-value"></a>Возвращаемое значение

Функция обратного вызова возвращает **int**. Это значение определяется пользователем. Если функция обратного вызова возвращает значение 0, `EnumObjects` останавливает перечисления раньше.

### <a name="remarks"></a>Примечания

Фактическое имя необходимо экспортировать.

## <a name="graystring"></a>  Функция обратного вызова для CDC::GrayString

*OutputFunc* — это имя функции обратного вызова, предоставляемую приложением.

### <a name="syntax"></a>Синтаксис

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>Параметры

*hDC*<br/>
Определяет контекст устройства памяти с растровым изображением по меньшей мере, ширины и высоты, заданной по `nWidth` и `nHeight` для `GrayString`.

*lpData*<br/>
Указывает на строку символов, которую необходимо нарисовать.

*nCount*<br/>
Указывает количество символов для вывода.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение функции обратного вызова, должно иметь значение TRUE в случае успеха; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Функция обратного вызова (*OutputFunc*) необходимо вывести изображение относительно координат (0,0) вместо (*x*, *y*).

## <a name="setabortproc"></a>  Функция обратного вызова для CDC::SetAbortProc

Имя *AbortFunc* — это имя функции, предоставляемую приложением.

### <a name="syntax"></a>Синтаксис

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>Параметры

*hPr*<br/>
Определяет контекст устройства.

*код*<br/>
Указывает, произошла ли ошибка. Это 0, если ошибки не произошло. Является SP_OUTOFDISK диспетчер печати уже недостаточно места на диске и места на диске будут доступны, если приложение ожидает. Если *кода* является SP_OUTOFDISK, приложение не имеет прервать задание печати. Если нет, она должна возвращать для диспетчера печати путем вызова `PeekMessage` или `GetMessage` функции Windows.

### <a name="return-value"></a>Возвращаемое значение

Функции обработчика прерывания возвращается ненулевое значение, если задание печати находится продолжить и 0, если его отмены.

### <a name="remarks"></a>Примечания

Фактическое имя необходимо экспортировать, как описано в разделе "Примечания" [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc).

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)

