---
title: Класс CSimpleException | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f25928243c8086462f4f35b47dee5239a3a240bf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447002"
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
|[CSimpleException::GetErrorMessage](#geterrormessage)|Содержит текст об ошибке, что произошло.|

## <a name="remarks"></a>Примечания

`CSimpleException` является базовым классом для исключений MFC, критическими ресурсами и обрабатывает владения и инициализации сообщения об ошибке. Следующие классы используют `CSimpleException` как базовый класс:

|||
|-|-|
|[Класс CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Исключение Out of memory|
|[Класс CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Запросы для неподдерживаемая операция|
|[Класс CResourceException](../../mfc/reference/cresourceexception-class.md)|Ресурс Windows, не найден или не создаваемый объект|
|[Класс CUserException](../../mfc/reference/cuserexception-class.md)|Исключение, которое указывает на ресурс не найден|
|[Класс CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Исключение, которое указывает недопустимый аргумент|

Так как `CSimpleException` — это абстрактный базовый класс, нельзя объявлять `CSimpleException` объекта напрямую. Вместо этого необходимо объявить производных объектов, например, в предыдущей таблице. Если вы объявляете производного класса, используйте предыдущий классы как модель.

Дополнительные сведения см. в разделе [класса CException](../../mfc/reference/cexception-class.md) раздела и [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CSimpleException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="csimpleexception"></a>  CSimpleException::CSimpleException

Конструктор.

```
CSimpleException();
explicit CSimpleException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Параметры

*bAutoDelete*<br/>
Укажите значение TRUE, если память для `CSimpleException` объект выделен в куче. Это приведет к `CSimpleException` объект будет удален при `Delete` функция-член вызывается для удаления исключение. Укажите значение FALSE, если `CSimpleException` объект находится в стеке или — это глобальный объект. В этом случае `CSimpleException` объект не будет удалено, когда `Delete` вызывается функция-член.

### <a name="remarks"></a>Примечания

Обычно никогда не потребовалось бы вызвать этот конструктор напрямую. Функция, которая создает исключение следует создать экземпляр `CException`-производного класса и вызвать его конструктор, или его необходимо использовать один из MFC вызвать исключение функции, такие как [AfxThrowFileException](exception-processing.md#afxthrowfileexception), могут породить предопределенного типа.

##  <a name="geterrormessage"></a>  CSimpleException::GetErrorMessage

Вызывайте эту функцию члена, чтобы предоставить текст об ошибке, которая произошла.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```

### <a name="parameters"></a>Параметры

*lpszError*<br/>
Указатель на буфер, который будет получать сообщение об ошибке.

*nMaxError*<br/>
Максимальное число символов, из которых может храниться в буфере, включая символ конца строки.

*pnHelpContext*<br/>
Адрес целое число без знака, который будет получать идентификатор контекста справки. Если значение равно NULL, возвращается идентификатор отсутствует.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0, если текст сообщения ошибки не доступен.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Обработка исключений](../../mfc/exception-handling-in-mfc.md)



