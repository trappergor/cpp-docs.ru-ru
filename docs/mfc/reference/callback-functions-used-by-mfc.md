---
title: Функции обратного вызова, используемые MFC
ms.date: 11/04/2016
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: 9e51774b2158a81fce05dc0bd27e296e4ad94faa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507701"
---
# <a name="callback-functions-used-by-mfc"></a>Функции обратного вызова, используемые MFC

В библиотека Microsoft Foundation Class появляются три функции обратного вызова. Эти функции обратного вызова передаются в [CDC:: енумобжектс](../../mfc/reference/cdc-class.md#enumobjects), [CDC:: грайстринг](../../mfc/reference/cdc-class.md#graystring)и [CDC:: SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc). Обратите внимание, что все функции обратного вызова должны перехватывать исключения MFC перед возвратом в Windows, так как исключения не могут быть вызваны через границы обратного вызова. Дополнительные сведения об исключениях см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

|name||
|----------|-----------------|
|[Функция обратного вызова для CDC::EnumObjects](#enum_objects)||
|[Функция обратного вызова для CDC::GrayString](#graystring)||
|[Функция обратного вызова для CDC::SetAbortProc](#setabortproc)||

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="enum_objects"></a>Функция обратного вызова для CDC:: Енумобжектс

Имя *обжектфунк* — это заполнитель для имени функции, предоставляемой приложением.

### <a name="syntax"></a>Синтаксис

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>Параметры

*лпсзлогобжект*<br/>
Указывает на структуру данных [LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen) или [логбруш](/windows/win32/api/wingdi/ns-wingdi-logbrush) , содержащую сведения об логических атрибутах объекта.

*лпдата*<br/>
Указывает на предоставляемые приложением данные, передаваемые `EnumObjects` в функцию.

### <a name="return-value"></a>Возвращаемое значение

Функция обратного вызова возвращает значение **типа int**. Значение этого возврата определяется пользователем. Если функция обратного вызова возвращает значение `EnumObjects` 0, то останавливает перечисление в начале.

### <a name="remarks"></a>Примечания

Действительное имя должно быть экспортировано.

## <a name="graystring"></a>Функция обратного вызова для CDC:: Грайстринг

*Аутпутфунк* — это заполнитель для имени функции обратного вызова, предоставляемого приложением.

### <a name="syntax"></a>Синтаксис

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>Параметры

*hDC*<br/>
Определяет контекст устройства памяти с точечным рисунком по ширине и высоте, указанным в `nWidth` параметре `GrayString`и `nHeight` .

*лпдата*<br/>
Указывает на строку символов, которую необходимо нарисовать.

*нкаунт*<br/>
Указывает количество символов для вывода.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение функции обратного вызова должно быть TRUE, чтобы обозначать успешность. в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Функция обратного вызова (*аутпутфунк*) должна рисовать изображение относительно координат (0, 0), а не (*x*, *y*).

## <a name="setabortproc"></a>Функция обратного вызова для CDC:: SetAbortProc

Имя *абортфунк* — это заполнитель для имени функции, предоставляемой приложением.

### <a name="syntax"></a>Синтаксис

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>Параметры

*хпр*<br/>
Определяет контекст устройства.

*код*<br/>
Указывает, произошла ли ошибка. Значение 0, если ошибка не возникла. Это SP_OUTOFDISK, если в диспетчере печати недостаточно места на диске, и в случае ожидания приложения становится доступным дополнительное дисковое пространство. Если *код* — SP_OUTOFDISK, приложению не придется прерывать задание печати. В противном случае он должен дать диспетчеру печати вызов `PeekMessage` функции или `GetMessage` Windows.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение функции прерывания-обработчика не равно нулю, если задание печати должно быть продолжено, и 0, если оно отменено.

### <a name="remarks"></a>Примечания

Фактическое имя должно быть экспортировано, как описано в разделе "Примечания" [CDC:: SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc).

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)
