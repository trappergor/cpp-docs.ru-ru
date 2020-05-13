---
title: Обработка исключений
ms.date: 11/04/2016
helpviewer_keywords:
- macros [MFC], exception handling
- DAO (Data Access Objects), exceptions [MFC]
- OLE exceptions [MFC], MFC functions
- exceptions [MFC], processing
- exception macros [MFC]
- termination functions, MFC
- MFC, exceptions
- exceptions [MFC], MFC throwing functions
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
ms.openlocfilehash: bdf9dee88c29621bdc77c83d2633d93b4b9d10a7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751609"
---
# <a name="exception-processing"></a>Обработка исключений

При выполнении программы может возникнуть ряд ненормальных условий и ошибок, называемых «исключениями». Они могут включать в себя запуск памяти, ошибки распределения ресурсов и неспособность найти файлы.

Библиотека класса Фонда Майкрософт использует схему обработки исключений, которая моделируется по образцу той, которая была предложена комитетом по стандартам ANSI для КЗ. Обработчик исключений должен быть настроен перед вызовом функции, которая может столкнуться с ненормальной ситуацией. Если функция сталкивается с ненормальным состоянием, она бросает исключение, и управление передается обработчику исключений.

Несколько макросов, включенных в библиотеку класса Microsoft Foundation, наведут обработчики исключений. Ряд других глобальных функций помогают бросать специализированные исключения и при необходимости прекращать программы. Эти макросы и глобальные функции подпадают под следующие категории:

- Макросы исключений, которые структурируют обработчик исключений.

- Функции, забрасывающие исключения), которые генерируют исключения определенных типов.

- Функции прекращения, которые вызывают прекращение программы.

Для примеров и более подробной [информации](../../mfc/exception-handling-in-mfc.md)см.

### <a name="exception-macros"></a>Исключение Макрос

|||
|-|-|
|[TRY](#try)|Назначает блок кода для обработки исключений.|
|[Поймать](#catch)|Назначает блок кода для ловли исключения из предыдущего блока **TRY.**|
|[CATCH_ALL](#catch_all)|Назначает блок кода для ловли всех исключений из предыдущего блока **TRY.**|
|[AND_CATCH](#and_catch)|Назначает блок кода для ловли дополнительных типов исключений из предыдущего блока **TRY.**|
|[AND_CATCH_ALL](#and_catch_all)|Назначает блок кода для ловли всех других дополнительных типов исключений, брошенных в предыдущий блок **TRY.**|
|[END_CATCH](#end_catch)|Завершает последний **блок кода CATCH** или **AND_CATCH.**|
|[END_CATCH_ALL](#end_catch_all)|Завершает последний **CATCH_ALL** блок кода.|
|[Бросить](#throw)|Бросает указанное исключение.|
|[THROW_LAST](#throw_last)|Бросает в настоящее время обработанное исключение для следующего внешнего обработчика.|

### <a name="exception-throwing-functions"></a>Функции исключения-бросая

|||
|-|-|
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Бросает исключение из архива.|
|[AfxThrowFileException](#afxthrowfileexception)|Бросает исключение файла.|
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|Бросает недействительное исключение аргумента.|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Бросает исключение памяти.|
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Бросает не поддерживаемое исключение.|
|[AfxThrowResourceException](#afxthrowresourceexception)|Бросает ненайденное исключение для ресурсов Windows.|
|[AfxThrowUserException](#afxthrowuserexception)|Бросает исключение в действие программы, инициированной пользователем.|

MFC предоставляет две функции, забрасывающие исключения специально для исключений OLE:

### <a name="ole-exception-functions"></a>Функции исключения OLE

|||
|-|-|
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|Делает исключение в функции автоматизации OLE.|
|[AfxThrowOleException](#afxthrowoleexception)|Бросает исключение OLE.|

Для поддержки исключений баз данных `CDBException` классы баз данных предоставляют два класса исключений и `CDaoException`глобальные функции для поддержки типов исключений:

### <a name="dao-exception-functions"></a>Функции исключения DAO

|||
|-|-|
|[AfxThrowDAOИсключение](#afxthrowdaoexception)|Бросает [CDaoException](../../mfc/reference/cdaoexception-class.md) из собственного кода.|
|[AfxThrowDBException](#afxthrowdbexception)|Бросает [CDBException](../../mfc/reference/cdbexception-class.md) из собственного кода.|

MFC предоставляет следующую функцию прекращения:

### <a name="termination-functions"></a>Функции прекращения

|||
|-|-|
|[AfxAbort](#afxabort)|Вызывается для завершения приложения при возникновении фатальной ошибки.|

## <a name="try"></a><a name="try"></a>Попробовать

Настраивает блок **TRY.**

```
TRY
```

### <a name="remarks"></a>Remarks

Блок **TRY** определяет блок кода, который может бросать исключения. Эти исключения обрабатываются в следующих **блоках CATCH** и **AND_CATCH.** Рекурсия разрешена: исключения могут передаваться внешнему блоку **TRY,** либо игнорируя их, либо используя THROW_LAST макрос. Завершите блок **TRY** END_CATCH или END_CATCH_ALL макросом.

Для получения дополнительной [информации](../../mfc/exception-handling-in-mfc.md)см.

### <a name="example"></a>Пример

Смотрите пример [CATCH](#catch).

### <a name="requirements"></a>Требования

Заголовок: afx.h

## <a name="catch"></a><a name="catch"></a>Поймать

Определяет блок кода, который ловит первый тип исключения, брошенный в предыдущем блоке **TRY.**

```
CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>Параметры

*exception_class*<br/>
Опознавательный тип исключения для тестирования. Для списка стандартных классов исключений см. [CException](../../mfc/reference/cexception-class.md)

*exception_object_pointer_name*<br/>
Укажите имя для указателя объектов исключения, который будет создан макросом. Имя указателя можно использовать для доступа к объекту исключения в блоке **CATCH.** Эта переменная объявлена для вас.

### <a name="remarks"></a>Remarks

Код обработки исключений может, при необходимости, допросить объект исключения, чтобы получить больше информации о конкретной причине исключения. Вызвать THROW_LAST макрос, чтобы перенести обработку на следующий внешний кадр исключения. Завершите блок **TRY** END_CATCH макросом.

Если *exception_class* является `CException`классом, то все типы исключений будут пойманы. Вы можете использовать [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) функции члена, чтобы определить, какое конкретно ежеисключениебыло. Лучший способ поймать несколько видов исключений — использовать последовательные **AND_CATCH** операторы, каждый из которых имеет другой тип исключения.

Указатель объекта исключения создается макросом. Вам не нужно объявлять об этом самостоятельно.

> [!NOTE]
> Блок **CATCH** определяется как область СЗ, очерченная скобками. Если вы объявляете переменные в этой области, они доступны только в этой области. Это также относится к *exception_object_pointer_name*.

Для получения дополнительной информации об исключениях [Exceptions](../../mfc/exception-handling-in-mfc.md)и макросе CATCH см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]

## <a name="catch_all"></a><a name="catch_all"></a>CATCH_ALL

Определяет блок кода, который ловит все типы исключений, брошенные в предыдущем блоке **TRY.**

```
CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Параметры

*exception_object_pointer_name*<br/>
Укажите имя для указателя объектов исключения, который будет создан макросом. Имя указателя можно использовать для доступа к `CATCH_ALL` объекту исключения в блоке. Эта переменная объявлена для вас.

### <a name="remarks"></a>Remarks

Код обработки исключений может, при необходимости, допросить объект исключения, чтобы получить больше информации о конкретной причине исключения. Вызвать `THROW_LAST` макрос для переноса обработки на следующий внешний кадр исключения. Если вы **используете CATCH_ALL,** конец блока **TRY** с END_CATCH_ALL макросом.

> [!NOTE]
> **Блок CATCH_ALL** определяется как область СЗ, очертаемая брекетами. Если вы объявляете переменные в этой области, они доступны только в этой области.

Для получения дополнительной информации об [Exceptions](../../mfc/exception-handling-in-mfc.md)исключениях см.

### <a name="example"></a>Пример

Смотрите пример [для CFile::Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="and_catch"></a><a name="and_catch"></a>AND_CATCH

Определяет блок кода для ловли дополнительных типов исключений, брошенных в предыдущем блоке **TRY.**

```
AND_CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>Параметры

*exception_class*<br/>
Опознавательный тип исключения для тестирования. Для списка стандартных классов исключений см. [CException](../../mfc/reference/cexception-class.md)

*exception_object_pointer_name*<br/>
Имя указателя объектов исключения, который будет создан макросом. Имя указателя можно использовать для доступа к объекту исключения в **AND_CATCH** блоке. Эта переменная объявлена для вас.

### <a name="remarks"></a>Remarks

Используйте макрос CATCH, чтобы поймать один тип исключения, а затем AND_CATCH макрос, чтобы поймать каждый последующий тип. Завершите блок **TRY** END_CATCH макросом.

Код обработки исключений может, при необходимости, допросить объект исключения, чтобы получить больше информации о конкретной причине исключения. Вызов THROW_LASTите макрос в **блоке AND_CATCH,** чтобы перенести обработку в следующий внешний кадр исключения. **AND_CATCH** отмечает конец предыдущего блока **CATCH** или **AND_CATCH.**

> [!NOTE]
> **Блок AND_CATCH** определяется как область СЗ (очертанапована фигурными скобками). Если вы декларируете переменные в этой области, помните, что они доступны только в пределах этой области. Это также относится к *exception_object_pointer_name* переменной.

### <a name="example"></a>Пример

Смотрите пример [CATCH](#catch).

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="and_catch_all"></a><a name="and_catch_all"></a>AND_CATCH_ALL

Определяет блок кода для ловли дополнительных типов исключений, брошенных в предыдущем блоке **TRY.**

```
AND_CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Параметры

*exception_object_pointer_name*<br/>
Имя указателя объектов исключения, который будет создан макросом. Имя указателя можно использовать для доступа к объекту исключения в **AND_CATCH_ALL** блоке. Эта переменная объявлена для вас.

### <a name="remarks"></a>Remarks

Используйте макрос **CATCH,** чтобы поймать один тип исключения, а затем AND_CATCH_ALL макрос, чтобы поймать все другие последующие типы. Если вы используете AND_CATCH_ALL, закончите блок **TRY** с END_CATCH_ALL макросом.

Код обработки исключений может, при необходимости, допросить объект исключения, чтобы получить больше информации о конкретной причине исключения. Вызовите THROW_LAST макрос в **AND_CATCH_ALL** блоке, чтобы перенести обработку в следующий внешний кадр исключения. **AND_CATCH_ALL** отмечает конец предыдущего блока **CATCH** или **AND_CATCH_ALL.**

> [!NOTE]
> **Блок AND_CATCH_ALL** определяется как область СЗ (очертана по скобкам). Если вы декларируете переменные в этой области, помните, что они доступны только в пределах этой области.

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="end_catch"></a><a name="end_catch"></a>END_CATCH

Отметки конца последнего **CATCH** или **AND_CATCH** блока.

```
END_CATCH
```

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о [Exceptions](../../mfc/exception-handling-in-mfc.md)END_CATCH макрос, см.

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="end_catch_all"></a><a name="end_catch_all"></a>END_CATCH_ALL

Отметки конца последнего **блока CATCH_ALL88** или **AND_CATCH_ALL.**

```
END_CATCH_ALL
```

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="throw-mfc"></a><a name="throw"></a>БРОСТО (MFC)

Бросает указанное исключение.

```
THROW(exception_object_pointer)
```

### <a name="parameters"></a>Параметры

*exception_object_pointer*<br/>
Очки к объекту исключения, полученному из `CException`.

### <a name="remarks"></a>Remarks

**THROW** прерывает выполнение программы, передавая управление связанного блоку **CATCH** в вашей программе. Если вы не предоставили блок **CATCH,** управление передается в модуль библиотеки Microsoft Foundation, который печатает сообщение об ошибке и выходит.

Для получения дополнительной [информации](../../mfc/exception-handling-in-mfc.md)см.

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="throw_last"></a><a name="throw_last"></a>THROW_LAST

Возвращает исключение обратно в следующий внешний блок **CATCH.**

```
THROW_LAST()
```

### <a name="remarks"></a>Remarks

Этот макрос позволяет выбросить локально созданное исключение. Если вы попытаетесь бросить исключение, которое вы только что поймали, он, как правило, выходят из сферы и быть удалены. С **THROW_LAST,** исключение передается правильно следующему обработчику **CATCH.**

Для получения дополнительной [информации](../../mfc/exception-handling-in-mfc.md)см.

### <a name="example"></a>Пример

Смотрите пример [для CFile::Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="afxthrowarchiveexception"></a><a name="afxthrowarchiveexception"></a>AfxThrowArchiveИсключительное исключение

Бросает исключение из архива.

```cpp
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName);
```

### <a name="parameters"></a>Параметры

*Вызвать*<br/>
Определяется несколько, которое указывает причину исключения. Список возможных значений можно узнать: [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).

*lpszArchiveName*<br/>
Точки строки, содержащей `CArchive` имя объекта, вызвавшего исключение (если он доступен).

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="afxthrowfileexception"></a><a name="afxthrowfileexception"></a>AfxThrowFileИсключениеисключение

Бросает исключение файла.

```cpp
void AfxThrowFileException(
    int cause,
    LONG lOsError = -1,
    LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Параметры

*Вызвать*<br/>
Определяется несколько, которое указывает причину исключения. Список возможных значений можно узнать: [CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause).

*lOsОшибка*<br/>
Содержит номер ошибки операционной системы (если он доступен), в котором указывается причина исключения. Ознакомьтесь с руководством операционной системы для перечисления кодов ошибок.

*lpszFileName*<br/>
Точки строки, содержащей имя файла, вызвавшего исключение (если он доступен).

### <a name="remarks"></a>Remarks

Вы несете ответственность за определение причины на основе кода ошибки операционной системы.

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="afxthrowinvalidargexception"></a><a name="afxthrowinvalidargexception"></a>AfxThrowInvalidargException

Бросает недействительное исключение аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
void AfxThrowInvalidArgException( );
```

### <a name="remarks"></a>Remarks

Эта функция вызывается при использовании недействительных аргументов.

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxthrowmemoryexception"></a><a name="afxthrowmemoryexception"></a>AfxThrowMemoryИсключение

Бросает исключение памяти.

```cpp
void AfxThrowMemoryException();
```

### <a name="remarks"></a>Remarks

Вызов ими, если вызовы на базовые системные системные системные системные системные системы -хозяйни (например, **malloc** и функция [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) Windows) сбой. Вам не нужно вызывать его для **нового,** потому что **новое** будет бросать исключение памяти автоматически, если распределение памяти не удается.

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="afxthrownotsupportedexception"></a><a name="afxthrownotsupportedexception"></a>AfxThrowNotSupportedИсключение

Выбрасывает исключение, которое является результатом запроса на неподдерживаемую функцию.

```cpp
void AfxThrowNotSupportedException();
```

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="afxthrowresourceexception"></a><a name="afxthrowresourceexception"></a>AfxThrowРесурс Исключение

Выбрасывает исключение ресурса.

```cpp
void  AfxThrowResourceException();
```

### <a name="remarks"></a>Remarks

Эта функция обычно вызывается, когда ресурс Windows не может быть загружен.

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="afxthrowuserexception"></a><a name="afxthrowuserexception"></a>AfxThrowUserИсключение

Бросает исключение, чтобы остановить операцию конечному пользователю.

```cpp
void AfxThrowUserException();
```

### <a name="remarks"></a>Remarks

Эта функция обычно вызывается `AfxMessageBox` сразу после сообщения об ошибке пользователю.

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="afxthrowoledispatchexception"></a><a name="afxthrowoledispatchexception"></a>AfxThrowOleDispatchИсключение

Используйте эту функцию, чтобы выбросить исключение в функции автоматизации OLE.

```cpp
void AFXAPI AfxThrowOleDispatchException(
    WORD wCode ,
    LPCSTR lpszDescription,
    UINT nHelpID = 0);

void AFXAPI AfxThrowOleDispatchException(
    WORD wCode,
    UINT nDescriptionID,
    UINT nHelpID = -1);
```

### <a name="parameters"></a>Параметры

*wКод*<br/>
Код ошибки, характерный для вашего приложения.

*lpszОписание*<br/>
Устное описание ошибки.

*nОписание*<br/>
Идентификатор ресурса для описания словесной ошибки.

*nHelpID*<br/>
Контекст справки для справки приложения (. HLP) файл.

### <a name="remarks"></a>Remarks

Информация, предоставляемая этой функции, может отображаться в приложении для вождения (Microsoft Visual Basic или другое клиентское приложение для автоматизации OLE).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="afxthrowoleexception"></a><a name="afxthrowoleexception"></a>AfxThrowOleИсключениесты

Создает объект типа `COleException` и бросает исключение.

```cpp
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr);
```

### <a name="parameters"></a>Параметры

*Sc*<br/>
Код состояния OLE, указывающий причину исключения.

*Hr*<br/>
Обработка кода результата, указывающем причину исключения.

### <a name="remarks"></a>Remarks

Версия, которая принимает HRESULT в качестве аргумента преобразует этот код результата в соответствующий SCODE. Для получения дополнительной информации о HRESULT и SCODE, [см. Структура кодов ошибки COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="afxthrowdaoexception"></a><a name="afxthrowdaoexception"></a>AfxThrowDaoИсключение

Вызовите эту функцию, чтобы выбросить исключение типа [CDaoException](../../mfc/reference/cdaoexception-class.md) из собственного кода.

```cpp
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,
    SCODE scode = S_OK);
```

### <a name="parameters"></a>Параметры

*nAfxDaoОшибка*<br/>
Огромное значение, представляющее расширенный код ошибки DAO, которое может быть одним из значений, перечисленных в [CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror).

*scode*<br/>
Код ошибки OLE от DAO, типа SCODE. Для получения информации, см [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode).

### <a name="remarks"></a>Remarks

Платформа также `AfxThrowDaoException`вызывает . В вашем вызове, вы можете пройти один из параметров или обоих. Например, если вы хотите поднять одну из ошибок, определенных в **CDaoException::nAfxDaoError,** но вы не заботитесь о параметре *scode,* передайте действительный код в параметре *nAfxDaoError* и примите значение по умолчанию для *scode.*

Для получения информации об исключениях, связанных с `CDaoException` классами MFC [Exceptions: Database Exceptions](../../mfc/exceptions-database-exceptions.md)DAO, см.

### <a name="requirements"></a>Требования

  **Заголовок** afxdb.h

## <a name="afxthrowdbexception"></a><a name="afxthrowdbexception"></a>AfxThrowDBException

Вызовите эту функцию, `CDBException` чтобы выбросить исключение типа из вашего собственного кода.

```cpp
void AfxThrowDBException(
    RETCODE nRetCode,
    CDatabase* pdb,
    HSTMT hstmt);
```

### <a name="parameters"></a>Параметры

*nRetCode*<br/>
Значение типа RETCODE, определяющее тип ошибки, вызвавшей бросив исключение.

*Pdb*<br/>
Указатель на `CDatabase` объект, представляющий соединение источника данных, с которым связано исключение.

*hstmt*<br/>
Ручка ODBC HSTMT, опозивающая ручку оператора, с которой связано исключение.

### <a name="remarks"></a>Remarks

Платформа вызывает `AfxThrowDBException` вызовы, когда она получает ODBC RETCODE от вызова к функции ODBC API и интерпретирует RETCODE как исключительное состояние, а не ожидаемую ошибку. Например, операция доступа к данным может вывести из строя из-за ошибки чтения диска.

Для получения информации о значениях RETCODE, определенных ODBC, см. Для получения информации о расширениях MFC [CDBException](../../mfc/reference/cdbexception-class.md)к этим кодам, см.

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="afxabort"></a><a name="afxabort"></a>AfxAbort

Функция прекращения по умолчанию, поставляемая MFC.

```cpp
void  AfxAbort();
```

### <a name="remarks"></a>Remarks

`AfxAbort`вызывается внутренне функциями члена MFC, когда есть фатальная ошибка, например непойманное исключение, с которым нельзя справиться. Вы можете `AfxAbort` вызвать вызов в редких случаях, когда вы столкнулись с катастрофической ошибкой, от которой вы не можете восстановиться.

### <a name="example"></a>Пример

Смотрите пример [CATCH](#catch).

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[Класс CException](cexception-class.md)<br/>
[Класс CInvalidargException](cinvalidargexception-class.md)
