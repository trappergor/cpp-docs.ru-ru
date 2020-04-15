---
title: Класс CArchiveException
ms.date: 11/04/2016
f1_keywords:
- CArchiveException
- AFX/CArchiveException
- AFX/CArchiveException::CArchiveException
- AFX/CArchiveException::m_cause
- AFX/CArchiveException::m_strFileName
helpviewer_keywords:
- CArchiveException [MFC], CArchiveException
- CArchiveException [MFC], m_cause
- CArchiveException [MFC], m_strFileName
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
ms.openlocfilehash: ad2a9d8c5b4466a04b5a88fcce7679911bf1b81a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377011"
---
# <a name="carchiveexception-class"></a>Класс CArchiveException

Представляет условие исключения сериализации

## <a name="syntax"></a>Синтаксис

```
class CArchiveException : public CException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CArchiveException::ArchiveException](#carchiveexception)|Формирует объект `CArchiveException`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CArchiveException::m_cause](#m_cause)|Указывает причину исключения.|
|[CArchiveException::m_strFileName](#m_strfilename)|Условляет сядее файла для этого состояния исключения.|

## <a name="remarks"></a>Remarks

Класс `CArchiveException` включает в себя общедоступный член данных, указывающий причину исключения.

`CArchiveException`объекты строятся и выбрасываются внутри функций членов [CArchive.](../../mfc/reference/carchive-class.md) Эти объекты можно получить в рамках выражения **CATCH.** Код причины не зависит от операционной системы. Для получения дополнительной информации [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md)об обработке исключений см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CArchiveException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="carchiveexceptioncarchiveexception"></a><a name="carchiveexception"></a>CArchiveException::ArchiveException

Строит `CArchiveException` объект, хранив аяризируя значение *причины* в объекте.

```
CArchiveException(
    int cause = CArchiveException::none,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Параметры

*cause*<br/>
Перечисленная переменная типа, указывающепричина причину исключения. Список регистраторов можно с [m_causeм.](#m_cause)

*lpszArchiveName*<br/>
Указывает на строку, содержащую имя `CArchive` объекта, вызывающего исключение.

### <a name="remarks"></a>Remarks

Вы можете `CArchiveException` создать объект на куче и бросить его самостоятельно или позволить глобальной функции [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) обрабатывать его за вас.

Не используйте этот конструктор напрямую; вместо этого вызов `AfxThrowArchiveException`глобальной функции.

## <a name="carchiveexceptionm_cause"></a><a name="m_cause"></a>CArchiveException::m_cause

Определяет причину исключения.

```
int m_cause;
```

### <a name="remarks"></a>Remarks

Этот член данных является общедоступной переменной типа **Int.** Его значения определяются `CArchiveException` перечисленным типом. Перечислители и их значение представлено далее.

- `CArchiveException::none`Ошибки не произошло.

- `CArchiveException::genericException`Неопределенная ошибка.

- `CArchiveException::readOnly`Пытался записать в архив, открытый для погрузки.

- `CArchiveException::endOfFile`Достигнуто окончание файла при чтении объекта.

- `CArchiveException::writeOnly`Пытался читать из архива, открытого для хранения.

- `CArchiveException::badIndex`Недействительный формат файла.

- `CArchiveException::badClass`Пытался считать объект в объект неправильного типа.

- `CArchiveException::badSchema`Пытался прочитать объект с другой версией класса.

    > [!NOTE]
    >  Перечислители причины `CArchiveException` отличаются от перечислителей причины `CFileException`.

    > [!NOTE]
    > `CArchiveException::generic` не рекомендуется к использованию. Используйте вместо этого `genericException`. Если **общий используется** в приложении и построен с /clr, будут ошибки синтаксиса, которые не легко расшифровать.

## <a name="carchiveexceptionm_strfilename"></a><a name="m_strfilename"></a>CArchiveException::m_strFileName

Условляет сядее файла для этого состояния исключения.

```
CString m_strFileName;
```

## <a name="see-also"></a>См. также раздел

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CArchive](../../mfc/reference/carchive-class.md)<br/>
[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)<br/>
[Обработка исключений](../../mfc/reference/exception-processing.md)
