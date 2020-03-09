---
title: Класс Карчивиксцептион
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
ms.openlocfilehash: 731735bccf9225e67d82b1fe90336c92a630b368
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855369"
---
# <a name="carchiveexception-class"></a>Класс Карчивиксцептион

Представляет условие исключения сериализации

## <a name="syntax"></a>Синтаксис

```
class CArchiveException : public CException
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Карчивиксцептион:: Карчивиксцептион](#carchiveexception)|Формирует объект `CArchiveException`.|

### <a name="public-data-members"></a>Открытые элементы данных

|Имя|Description|
|----------|-----------------|
|[Карчивиксцептион:: m_cause](#m_cause)|Указывает причину исключения.|
|[Карчивиксцептион:: m_strFileName](#m_strfilename)|Указывает имя файла для этого условия исключения.|

## <a name="remarks"></a>Remarks

Класс `CArchiveException` содержит открытый элемент данных, указывающий причину исключения.

`CArchiveException` объекты создаются и создаются в функциях элементов [CArchive](../../mfc/reference/carchive-class.md) . Доступ к этим объектам можно получить в области выражения **catch** . Код причины не зависит от операционной системы. Дополнительные сведения об обработке исключений см. в разделе [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CArchiveException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="carchiveexception"></a>Карчивиксцептион:: Карчивиксцептион

Конструирует объект `CArchiveException`, сохраняя значение *причины* в объекте.

```
CArchiveException(
    int cause = CArchiveException::none,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Параметры

*cause*<br/>
Переменная перечислимого типа, указывающая причину исключения. Список перечислителей см. в разделе элемент данных [m_cause](#m_cause) .

*лпсзарчивенаме*<br/>
Указывает на строку, содержащую имя объекта `CArchive`, вызвавшего исключение.

### <a name="remarks"></a>Remarks

Вы можете создать объект `CArchiveException` в куче и создать его самостоятельно или позволить глобальной функции [афкссроварчивиксцептион](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) его обработку.

Не используйте этот конструктор напрямую; Вместо этого вызовите глобальную функцию `AfxThrowArchiveException`.

##  <a name="m_cause"></a>Карчивиксцептион:: m_cause

Указывает причину исключения.

```
int m_cause;
```

### <a name="remarks"></a>Remarks

Этот элемент данных является открытой переменной типа **int**. Его значения определяются `CArchiveException` перечисляемым типом. Перечислители и их значение представлено далее.

- `CArchiveException::none` ошибок не возникло.

- Неопределенная ошибка `CArchiveException::genericException`.

- `CArchiveException::readOnly` попытка записи в архив, Открытый для загрузки.

- `CArchiveException::endOfFile` достигнут конец файла при чтении объекта.

- `CArchiveException::writeOnly` попытались выполнить чтение из архива, открытого для хранения.

- `CArchiveException::badIndex` недопустимый формат файла.

- `CArchiveException::badClass` пытался считать объект в объект неправильного типа.

- `CArchiveException::badSchema` пытался считать объект с другой версией класса.

    > [!NOTE]
    >  Перечислители причины `CArchiveException` отличаются от перечислителей причины `CFileException`.

    > [!NOTE]
    > `CArchiveException::generic` не рекомендуется к использованию. Используйте вместо этого `genericException`. Если **универсальное** приложение используется в приложении и строится с помощью параметра/CLR, то будут отображаться синтаксические ошибки, которые непросто расшифровать.

##  <a name="m_strfilename"></a>Карчивиксцептион:: m_strFileName

Указывает имя файла для этого условия исключения.

```
CString m_strFileName;
```

## <a name="see-also"></a>См. также раздел

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CArchive](../../mfc/reference/carchive-class.md)<br/>
[афкссроварчивиксцептион](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)<br/>
[Обработка исключений](../../mfc/reference/exception-processing.md)
