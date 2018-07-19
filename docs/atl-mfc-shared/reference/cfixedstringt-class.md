---
title: Класс CFixedStringT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6b47642965b73662e63a839796425be855a6523
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879531"
---
# <a name="cfixedstringt-class"></a>Класс CFixedStringT
Этот класс представляет строковый объект с помощью фиксированного символьного буфера.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```  
  
#### <a name="parameters"></a>Параметры  
 *StringType*  
 Используется в качестве базового класса для фиксированной строки объекта и может быть любым `CStringT`-тип данных на основе. Некоторые примеры включают `CString`, `CStringA`, и `CStringW`.  
  
 *t_nChars*  
 Число символов, сохраненных в буфере.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFixedStringT::CFixedStringT](#cfixedstringt)|Конструктор для создаваемого строкового объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFixedStringT::operator =](#eq)|Назначает новое значение для `CFixedStringT` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является примером класса пользовательскую строку, на основе `CStringT`. Несмотря на то что очень похожа, эти два класса отличаются в реализации. Основные отличия `CFixedStringT` и `CStringT` являются:  
  
-   Буфер исходного символа, выделяется как часть объекта и имеет размер *t_nChars*. Это позволяет `CFixedString` объект занимают блок непрерывной памяти для повышения производительности. Тем не менее если содержимое `CFixedStringT` превышении объект *t_nChars*, динамическое выделение памяти буфера.  
  
-   Буфер символов для `CFixedStringT` объекта, всегда имеют одинаковую длину ( *t_nChars*). Нет ограничений на размер буфера для `CStringT` объектов.  
  
-   Диспетчер памяти для `CFixedStringT` настраивается таким образом, общий доступ к [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) объекта между двумя или несколькими `CFixedStringT` objectsis не допускается. `CStringT` объекты не имеют этого ограничения.  
  
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
CFixedStringT(const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT(const StringType& str);
CFixedStringT(const StringType::XCHAR* psz);
explicit CFixedStringT(const StringType::YCHAR* psz);
explicit CFixedStringT(const unsigned char* psz);
```  
  
### <a name="parameters"></a>Параметры  
 *psz*  
 Заканчивающуюся нулем строку, который необходимо скопировать в это `CFixedStringT` объекта.  
  
 *str*  
 Существующий `CFixedStringT` объект, который необходимо скопировать в это `CFixedStringT` объекта.  
  
 *pStringMgr*  
 Указатель на диспетчер памяти `CFixedStringT` объекта. Дополнительные сведения о `IAtlStringMgr` и управление памятью для `CFixedStringT`, см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
### <a name="remarks"></a>Примечания  
 Поскольку конструкторы копируют входные данные в новый объем выделенного хранилища, следует иметь в виду, что память, может привести к исключения. Обратите внимание на то, что некоторые из этих конструкторов выступать в качестве функции преобразования.  
  
##  <a name="operator__eq"></a>  CFixedStringT::operator =  
 Повторно инициализирует существующий `CFixedStringT` объект новыми данными.  
  
```
CFixedStringT<StringType, t_nChars>& operator=(
  const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT<StringType, t_nChars>& operator=(const char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* psz);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& str);
```  
  
### <a name="parameters"></a>Параметры  
 *str*  
 Заканчивающуюся нулем строку, который необходимо скопировать в это `CFixedStringT` объекта.  
  
 *psz*  
 Существующий `CFixedStringT` копируются в это `CFixedStringT` объекта.  
  
### <a name="remarks"></a>Примечания  
 Следует иметь в виду, памяти, могут возникать исключения, каждый раз при использовании оператора присваивания, так как часто выделяется новая память для хранения результирующего `CFixedStringT` объекта.  
  
## <a name="see-also"></a>См. также  
 [Класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)




