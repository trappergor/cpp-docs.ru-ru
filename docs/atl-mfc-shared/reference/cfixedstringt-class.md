---
title: Класс CFixedStringT
ms.date: 03/27/2019
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
ms.openlocfilehash: 6c7649b7131e3b1620112acf89867d0731d7265d
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58564870"
---
# <a name="cfixedstringt-class"></a>Класс CFixedStringT

Этот класс представляет строковый объект с помощью фиксированного символьного буфера.

## <a name="syntax"></a>Синтаксис

```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```

#### <a name="parameters"></a>Параметры

*StringType*<br/>
Используется в качестве базового класса для фиксированной строки объекта и может быть любым `CStringT`-тип данных на основе. Некоторые примеры включают `CString`, `CStringA`, и `CStringW`.

*t_nChars*<br/>
Число символов, сохраненных в буфере.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CFixedStringT::CFixedStringT](#cfixedstringt)|Конструктор для создаваемого строкового объекта.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CFixedStringT::operator =](#operator_eq)|Назначает новое значение для `CFixedStringT` объекта.|

## <a name="remarks"></a>Примечания

Этот класс является примером класса пользовательскую строку, на основе `CStringT`. Хотя они похожи, эти два класса отличаются в реализации. Основные отличия `CFixedStringT` и `CStringT` являются:

- Буфер исходного символа, выделяется как часть объекта и имеет размер *t_nChars*. Это позволяет `CFixedString` объект занимают блок непрерывной памяти для повышения производительности. Тем не менее если содержимое `CFixedStringT` превышении объект *t_nChars*, динамическое выделение памяти буфера.

- Буфер символов для `CFixedStringT` объекта, всегда имеют одинаковую длину ( *t_nChars*). Нет ограничений на размер буфера для `CStringT` объектов.

- Диспетчер памяти для `CFixedStringT` настраивается таким образом, общий доступ к [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) объекта между двумя или несколькими `CFixedStringT` объектов не допускается. `CStringT` объекты не имеют этого ограничения.

Дополнительные сведения о настройке `CFixedStringT` и управление памятью для строковых объектов в целом, см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlStringMgr`

`StringType`

`CFixedStringMgr`

`CFixedStringT`

## <a name="requirements"></a>Требования

**Заголовок:** cstringt.h

##  <a name="cfixedstringt"></a>  CFixedStringT::CFixedStringT

Создает объект `CFixedStringT`.

```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT(const StringType& strSrc);
CFixedStringT(const StringType::XCHAR* pszSrc);
explicit CFixedStringT(const StringType::YCHAR* pszSrc);
explicit CFixedStringT(const unsigned char* pszSrc);
```

### <a name="parameters"></a>Параметры

*pszSrc*<br/>
Заканчивающуюся нулем строку, который необходимо скопировать в это `CFixedStringT` объекта.

*strSrc*<br/>
Существующий `CFixedStringT` объект, который необходимо скопировать в это `CFixedStringT` объекта.

*pStringMgr*<br/>
Указатель на диспетчер памяти `CFixedStringT` объекта. Дополнительные сведения о `IAtlStringMgr` и управление памятью для `CFixedStringT`, см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

### <a name="remarks"></a>Примечания

Поскольку конструкторы копируют входные данные в новый объем выделенного хранилища, следует иметь в виду, что память, может привести к исключения. Некоторые из этих конструкторов в качестве функции преобразования.

##  <a name="operator_eq"></a>  CFixedStringT::operator =

Повторно инициализирует существующий `CFixedStringT` объект новыми данными.

```
CFixedStringT<StringType, t_nChars>& operator=(
    const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT<StringType, t_nChars>& operator=(const char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& strSrc);
```

### <a name="parameters"></a>Параметры

*pszSrc*<br/>
Заканчивающуюся нулем строку, который необходимо скопировать в это `CFixedStringT` объекта.

*strSrc*<br/>
Существующий `CFixedStringT` копируются в это `CFixedStringT` объекта.

### <a name="remarks"></a>Примечания

Следует иметь в виду, памяти, могут возникать исключения, каждый раз при использовании оператора присваивания, так как часто выделяется новая память для хранения результирующего `CFixedStringT` объекта.

## <a name="see-also"></a>См. также

[Класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
