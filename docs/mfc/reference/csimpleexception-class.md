---
title: Класс CSimpleException
ms.date: 11/04/2016
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
ms.openlocfilehash: eb94ba9e3d26b3cd910f23c3d4abb29d3b8b1cd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318364"
---
# <a name="csimpleexception-class"></a>Класс CSimpleException

Этот класс является базовым классом для исключений MFC, связанных с критическими ресурсами.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CSimpleException : public CException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSimpleException::CSimpleException](#csimpleexception)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleException::GetErrorMessage](#geterrormessage)|Предоставляет текст об ошибке, которая произошла.|

## <a name="remarks"></a>Remarks

`CSimpleException`является базовым классом для ресурсо-критических исключений MFC и обрабатывает владение и инициализацию сообщения об ошибке. Следующие классы используются `CSimpleException` в качестве базового класса:

|||
|-|-|
|[Класс CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Исключение из памяти|
|[Класс CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Запросы на неподдерживаемую операцию|
|[Класс CResourceException](../../mfc/reference/cresourceexception-class.md)|Ресурс Windows не найден или не способен к соотвене|
|[Класс CUserException](../../mfc/reference/cuserexception-class.md)|Исключение, указываво еде, не может быть найдено|
|[Класс CInvalidargException](../../mfc/reference/cinvalidargexception-class.md)|Исключение, указываво недействительный аргумент|

Поскольку `CSimpleException` это абстрактный базовый класс, вы не можете объявить `CSimpleException` объект напрямую. Вместо этого необходимо декларировать производные объекты, такие как объекты предыдущей таблицы. Если вы объявляете свой собственный класс, используйте предыдущие классы в качестве модели.

Для получения дополнительной [CException Class](../../mfc/reference/cexception-class.md) информации см. [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CSimpleException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="csimpleexceptioncsimpleexception"></a><a name="csimpleexception"></a>CSimpleException::CSimpleException

Конструктор.

```
CSimpleException();
explicit CSimpleException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Параметры

*bAutoDelete*<br/>
Укажите TRUE, если `CSimpleException` память для объекта была выделена на куче. Это приведет `CSimpleException` к удалению объекта `Delete` при вызове функции участника для удаления исключения. Укажите FALSE, находится ли `CSimpleException` объект в стеке или является глобальным объектом. В этом случае `CSimpleException` объект не будет удален `Delete` при вызове функции участника.

### <a name="remarks"></a>Remarks

Обычно вам никогда не нужно звонить этому конструктору напрямую. Функция, которая бросает исключение, должна создать `CException`экземпляр класса, полученного из-производного, или вызвать его конструктор, или она должна использовать одну из функций метания MFC, такую как [AfxThrowFileException](exception-processing.md#afxthrowfileexception), чтобы бросить предопределенный тип.

## <a name="csimpleexceptiongeterrormessage"></a><a name="geterrormessage"></a>CSimpleException::GetErrorMessage

Вызовите эту функцию участника, чтобы предоставить текст об ошибке, которая произошла.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```

### <a name="parameters"></a>Параметры

*lpszОшибка*<br/>
Указатель на буфер, который получит сообщение об ошибке.

*nMaxОшибка*<br/>
Максимальное количество символов, которые может держать буфер, включая терминатор NULL.

*pnHelpКонтекст*<br/>
Адрес UINT, который получит идентификатор контекста справки. Если NULL, идентификатор не будет возвращен.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешна; в противном случае 0, если текст сообщения об ошибке недоступен.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации [см. CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Обработка исключений](../../mfc/exception-handling-in-mfc.md)
