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
ms.openlocfilehash: 6fe475ebd90ff13fec6a2835b6fdd4cf3d6034a4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476885"
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
|[CArchiveException::CArchiveException](#carchiveexception)|Создает объект `CArchiveException`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CArchiveException::m_cause](#m_cause)|Указывает причину исключения.|
|[CArchiveException::m_strFileName](#m_strfilename)|Указывает имя файла для данного условия исключения.|

## <a name="remarks"></a>Примечания

`CArchiveException` Класс включает в себя членом открытых данных, которые указывают на причину исключения.

`CArchiveException` объекты конструирования и исключения внутри [CArchive](../../mfc/reference/carchive-class.md) функций-членов. Эти объекты в пределах доступны **CATCH** выражение. Код причины не зависит от операционной системы. Дополнительные сведения об обработке исключений см. в разделе [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CArchiveException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="carchiveexception"></a>  CArchiveException::CArchiveException

Создает `CArchiveException` объекта, при сохранении значения *вызвать* в объекте.

```
CArchiveException(
    int cause = CArchiveException::none,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Параметры

*Причина*<br/>
Переменной перечисляемого типа, указывающее причину возникновения исключения. Список перечислителей, см. в разделе [m_cause](#m_cause) данные-член.

*lpszArchiveName*<br/>
Указывает на строку, содержащую имя `CArchive` объекта, вызвавшего исключение.

### <a name="remarks"></a>Примечания

Можно создать `CArchiveException` объекта в куче и передать его самостоятельно или позволить глобальную функцию [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) обработать его для вас.

Не используйте этот конструктор напрямую. Вместо этого вызовите глобальную функцию `AfxThrowArchiveException`.

##  <a name="m_cause"></a>  CArchiveException::m_cause

Указывает причину исключения.

```
int m_cause;
```

### <a name="remarks"></a>Примечания

Этот элемент данных — это открытая переменная типа **int**. Его значения определяются `CArchiveException` перечисляемый тип. Перечислители и их значение представлено далее.

- `CArchiveException::none` Ошибки не обнаружены.

- `CArchiveException::genericException` Неизвестная ошибка.

- `CArchiveException::readOnly` Попытка записи в архиве, открытом для загрузки.

- `CArchiveException::endOfFile` Достигнут конец файла при чтении объекта.

- `CArchiveException::writeOnly` Попытка чтения из архива открыт для хранения.

- `CArchiveException::badIndex` Недопустимый формат файла.

- `CArchiveException::badClass` Предпринята попытка считать объект в объект неверного типа.

- `CArchiveException::badSchema` Предпринята попытка считать объект с другой версией класса.

    > [!NOTE]
    >  Перечислители причины `CArchiveException` отличаются от перечислителей причины `CFileException`.

    > [!NOTE]
    > `CArchiveException::generic` не рекомендуется к использованию. Взамен рекомендуется использовать `genericException`. Если **универсального** приложения и построения с/CLR, будет синтаксических ошибок, которые не являются нелегко расшифровать.

##  <a name="m_strfilename"></a>  CArchiveException::m_strFileName

Указывает имя файла для данного условия исключения.

```
CString m_strFileName;
```

## <a name="see-also"></a>См. также

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CArchive](../../mfc/reference/carchive-class.md)<br/>
[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)<br/>
[Обработка исключений](../../mfc/reference/exception-processing.md)

