---
title: Класс COleDispatchException
ms.date: 11/04/2016
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
helpviewer_keywords:
- COleDispatchException [MFC], m_dwHelpContext
- COleDispatchException [MFC], m_strDescription
- COleDispatchException [MFC], m_strHelpFile
- COleDispatchException [MFC], m_strSource
- COleDispatchException [MFC], m_wCode
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
ms.openlocfilehash: 06f8d8abd8ea337369ceed62a9944e867d355768
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456242"
---
# <a name="coledispatchexception-class"></a>Класс COleDispatchException

Обрабатывает исключения, относящиеся к интерфейсу OLE `IDispatch` и являющиеся ключевой частью OLE-автоматизации.

## <a name="syntax"></a>Синтаксис

```
class COleDispatchException : public CException
```

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COleDispatchException::m_dwHelpContext](#m_dwhelpcontext)|Контекст справки для ошибки.|
|[COleDispatchException::m_strDescription](#m_strdescription)|Описание устные ошибки.|
|[COleDispatchException::m_strHelpFile](#m_strhelpfile)|Файл для использования с справки `m_dwHelpContext`.|
|[COleDispatchException::m_strSource](#m_strsource)|Приложения, создавшего исключение.|
|[COleDispatchException::m_wCode](#m_wcode)|`IDispatch`-конкретный код ошибки.|

## <a name="remarks"></a>Примечания

Как и другие классы исключений, производные от `CException` базового класса, `COleDispatchException` может использоваться с THROW, THROW_LAST, TRY, CATCH, AND_CATCH и END_CATCH макросы.

Как правило, следует вызывать [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) Чтобы создать и вызвать `COleDispatchException` объекта.

Дополнительные сведения об исключениях см. в статьях [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md) и [исключений: исключения OLE](../../mfc/exceptions-ole-exceptions.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleDispatchException`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="m_dwhelpcontext"></a>  COleDispatchException::m_dwHelpContext

Определяет контекст справки в справке вашего приложения (. Файл HLP).

```
DWORD m_dwHelpContext;
```

### <a name="remarks"></a>Примечания

Этот член задан с помощью функции [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) когда возникает исключение.

### <a name="example"></a>Пример

  См. пример для [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

##  <a name="m_strdescription"></a>  COleDispatchException::m_strDescription

Содержит описание устные ошибки, например «Диск заполнен».

```
CString m_strDescription;
```

### <a name="remarks"></a>Примечания

Этот член задан с помощью функции [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) когда возникает исключение.

### <a name="example"></a>Пример

  См. пример для [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

##  <a name="m_strhelpfile"></a>  COleDispatchException::m_strHelpFile

Автоматически заполняются в эту строку с именем файла справки приложения.

```
CString m_strHelpFile;
```

##  <a name="m_strsource"></a>  COleDispatchException::m_strSource

Автоматически заполняются в эту строку с именем приложения, создавшего исключение.

```
CString m_strSource;
```

### <a name="example"></a>Пример

  См. пример для [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

##  <a name="m_wcode"></a>  COleDispatchException::m_wCode

Содержит код ошибки, характерные для вашего приложения.

```
WORD m_wCode;
```

### <a name="remarks"></a>Примечания

Этот член задан с помощью функции [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) когда возникает исключение.

## <a name="see-also"></a>См. также

[Пример MFC CALCDRIV](../../visual-cpp-samples.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)<br/>
[Класс COleException](../../mfc/reference/coleexception-class.md)
