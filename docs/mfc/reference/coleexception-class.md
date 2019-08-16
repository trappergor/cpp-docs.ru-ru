---
title: Класс COleException
ms.date: 11/04/2016
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
ms.openlocfilehash: 96061f704d9df6cd788e362652b6ed22a7ffa999
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503951"
---
# <a name="coleexception-class"></a>Класс COleException

Представляет исключительное условие, связанное с операцией OLE.

## <a name="syntax"></a>Синтаксис

```
class COleException : public CException
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleException::P шаблоны](#process)|Преобразует Перехваченное исключение в код возврата OLE.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[COleException:: m_sc](#m_sc)|Содержит код состояния, указывающий причину исключения.|

## <a name="remarks"></a>Примечания

`COleException` Класс включает открытый элемент данных, содержащий код состояния, указывающий причину исключения.

Как `COleException` правило, не следует создавать объект напрямую; вместо этого следует вызывать [афкссроволиксцептион](exception-processing.md#afxthrowoleexception).

Дополнительные сведения об исключениях см. в статьях [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md) и [исключения. Исключения](../../mfc/exceptions-ole-exceptions.md)OLE.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleException`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="m_sc"></a>COleException:: m_sc

Этот элемент данных содержит код состояния OLE, указывающий причину исключения.

```
SCODE m_sc;
```

### <a name="remarks"></a>Примечания

Значение этой переменной задается параметром [афкссроволиксцептион](exception-processing.md#afxthrowoleexception).

Дополнительные сведения о SCODE см. в разделе [структура кодов ошибок COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]

##  <a name="process"></a>COleException::P шаблоны

Вызовите функцию-член **Process** , чтобы перевести Перехваченное исключение в код состояния OLE.

```
static SCODE PASCAL Process(const CException* pAnyException);
```

### <a name="parameters"></a>Параметры

*панексцептион*<br/>
Указатель на Перехваченное исключение.

### <a name="return-value"></a>Возвращаемое значение

Код состояния OLE.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  Эта функция является **статической**.

Дополнительные сведения о SCODE см. в разделе [структура кодов ошибок COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

### <a name="example"></a>Пример

  См. пример для [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

## <a name="see-also"></a>См. также

[Пример CALCDRIV в MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
