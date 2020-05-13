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
ms.openlocfilehash: 737c9e669990f4de6ae18cdc7662c131ad61516f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375012"
---
# <a name="coleexception-class"></a>Класс COleException

Представляет исключительное условие, связанное с операцией OLE.

## <a name="syntax"></a>Синтаксис

```
class COleException : public CException
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleException::Process](#process)|Переводит пойманное исключение в код возврата OLE.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COleException::m_sc](#m_sc)|Содержит код состояния, указывающий причину исключения.|

## <a name="remarks"></a>Remarks

Класс `COleException` включает в себя общедоступный член данных, который содержит код статуса с указанием причины исключения.

Как правило, не следует `COleException` создавать объект напрямую; вместо этого, вы должны вызвать [AfxThrowOleException](exception-processing.md#afxthrowoleexception).

Для получения дополнительной информации об [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md) исключениях см. [Exceptions: OLE Exceptions](../../mfc/exceptions-ole-exceptions.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleException`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="coleexceptionm_sc"></a><a name="m_sc"></a>COleException::m_sc

Этот участник данных содержит код состояния OLE, указывающий причину исключения.

```
SCODE m_sc;
```

### <a name="remarks"></a>Remarks

Значение этой переменной устанавливается [AfxThrowOleException](exception-processing.md#afxthrowoleexception).

Для получения дополнительной информации о SCODE, [см. Структура кодов ошибки COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]

## <a name="coleexceptionprocess"></a><a name="process"></a>COleException::Process

Вызовите функцию участника **процесса,** чтобы перевести пойманное исключение в код статуса OLE.

```
static SCODE PASCAL Process(const CException* pAnyException);
```

### <a name="parameters"></a>Параметры

*pAnyException*<br/>
Указатель на пойманное исключение.

### <a name="return-value"></a>Возвращаемое значение

Код состояния OLE.

### <a name="remarks"></a>Remarks

> [!NOTE]
> Эта функция **является статической**.

Для получения дополнительной информации о SCODE, [см. Структура кодов ошибки COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

### <a name="example"></a>Пример

  См. пример для [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

## <a name="see-also"></a>См. также раздел

[MFC Пример CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
