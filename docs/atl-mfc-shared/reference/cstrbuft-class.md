---
title: "Класс CStrBufT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CStrBufT<TCharType>
- ATL.CStrBufT
- CStrBufT
- ATL::CStrBufT
- ATL.CStrBufT<TCharType>
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 2eb551d2db029de88aa9c1b456c44609b7fc0922
ms.lasthandoff: 02/24/2017

---
# <a name="cstrbuft-class"></a>Класс CStrBufT
Этот класс предоставляет ресурсов автоматической очистки для `GetBuffer` и `ReleaseBuffer` вызывает на существующем `CStringT` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename TCharType>
class CStrBufT
```  
  
#### <a name="parameters"></a>Параметры  
 *TCharType*  
 Тип символа для `CStrBufT` класса. Ниже указаны доступные значения.  
  
- `char`(для символьных строк ANSI)  
  
- `wchar_t`(для символьных строк в Юникоде)  
  
- **TCHAR** (для символьных строк ANSI или Юникод)  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`PCXSTR`|Указатель на строковую константу.|  
|`PXSTR`|Указатель на строку.|  
|`StringType`|Тип строки, буфер управляться специализации шаблона класса.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStrBufT::CStrBufT](#cstrbuft)|Конструктор для объекта буфера строки.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStrBufT::SetLength](#setlength)|Задает длину буфера символ соответствующий строковый объект.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStrBufT::operator PCXSTR](#operator_pcxstr)|Извлекает **const** указатель на буфер символов связанные строкового объекта.|  
|[CStrBufT::operator PXSTR](#operator_pxstr)|Извлекает указатель на буфер символов связанные строкового объекта.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStrBufT::AUTO_LENGTH](#auto_length)|Автоматически определите новую длину строки на момент выпуска.|  
|[CStrBufT::SET_LENGTH](#set_length)|Задайте длину строкового объекта во время GetBuffer|  
  
## <a name="remarks"></a>Примечания  
 Этот класс используется как класс-оболочку для замены вызовов [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) и [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer), или [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) и `ReleaseBuffer`.  
  
 Разрабатывалась в качестве вспомогательного класса `CStrBufT` предоставляет удобный способ для разработчиков для работы с буфер символов строкового объекта, не беспокоясь о том, как и когда следует вызывать `ReleaseBuffer`. Это можно сделать, так как объект-оболочка выходит за пределы области естественным образом в случае исключения или несколько путей существующий код; вызывает деструктор для освобождения строкового ресурса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpstr.h  
  
##  <a name="a-nameautolengtha--cstrbuftautolength"></a><a name="auto_length"></a>CStrBufT::AUTO_LENGTH  
 Автоматически определите новую длину строки на момент выпуска.  
  
```
static const DWORD AUTO_LENGTH = 0x01;
```  
  
### <a name="remarks"></a>Примечания  
 Автоматически определите новую длину строки на момент выпуска. Строка должна быть нулем.  
  
##  <a name="a-namecstrbufta--cstrbuftcstrbuft"></a><a name="cstrbuft"></a>CStrBufT::CStrBufT  
 Создает объект буфера.  
  
```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Строковый объект, связанный с буфером. Как правило, разработчик будет использовать предопределенные определения типов для **CStrBuf** ( **TCHAR** вариант), **CStrBufA** ( `char` вариант) и **CStrBufW** ( `wchar_t` вариант).  
  
 *nMinLength*  
 Минимальная длина буфера символов.  
  
 `dwFlags`  
 Определяет, если длина строки определяется автоматически. Ниже указаны доступные значения.  
  
- **AUTO_LENGTH** длина строки составляет автоматически определяется при [CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) вызывается. Строка должна быть нулем. Значение по умолчанию.  
  
- **SET_LENGTH** строку, длина устанавливается при [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) вызывается.  
  
### <a name="remarks"></a>Примечания  
 Создает строковый буфер для связанной строки объекта. Во время построения [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) или [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) вызывается.  
  
 Обратите внимание, что конструктор копии `private`.  
  
##  <a name="a-nameoperatorpcxstra--cstrbuftoperator-pcxstr"></a><a name="operator_pcxstr"></a>CStrBufT::operator PCXSTR  
 Напрямую обращается к символов, сохраненных в соответствующий строковый объект как строки в стиле C.  
  
```  
operator PCXSTR() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель символа строки данных.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает указатель на буфер символов строкового объекта. Содержимое строкового объекта невозможно этого указателя.  
  
##  <a name="a-nameoperatorpxstra--cstrbuftoperator-pxstr"></a><a name="operator_pxstr"></a>CStrBufT::operator PXSTR  
 Напрямую обращается к символов, сохраненных в соответствующий строковый объект как строки в стиле C.  
  
```
operator PXSTR() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель символа строки данных.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает указатель на буфер символов строкового объекта. Разработчик может изменить содержимое объекта string с указателем.  
  
##  <a name="a-namepcxstra--cstrbuftpcxstr"></a><a name="pcxstr"></a>CStrBufT::PCXSTR  
 Указатель на строковую константу.  
  
```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```  
  
##  <a name="a-namepxstra--cstrbuftpxstr"></a><a name="pxstr"></a>CStrBufT::PXSTR  
 Указатель на строку.  
  
```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```  
  
##  <a name="a-namesetlengtha--cstrbuftsetlength"></a><a name="set_length"></a>CStrBufT::SET_LENGTH  
 Задайте длину строкового объекта в `GetBuffer` время.  
  
```
static const DWORD SET_LENGTH = 0x02;
```  
  
### <a name="remarks"></a>Примечания  
 Задайте длину строкового объекта во время GetBuffer.  
  
 Определяет, если [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) и [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) вызываются, когда создается объект буфера строки.  
  
##  <a name="a-namesetlengtha--cstrbuftsetlength"></a><a name="setlength"></a>CStrBufT::SetLength  
 Задает длину буфера знаков.  
  
```
void SetLength(int nLength);
```  
  
### <a name="parameters"></a>Параметры  
 `nLength`  
 Новая длина буфера символ объекта string.  
  
> [!NOTE]
>  Должно быть меньше или равно минимальное буфера длины, указанной в конструкторе `CStrBufT`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для задания длины строки, представленный объектом буфера.  
  
##  <a name="a-namestringtypea--cstrbuftstringtype"></a><a name="stringtype"></a>CStrBufT::StringType  
 Тип строки, буфер управляться специализации шаблона класса.  
  
```
typedef CSimpleStringT<TCharType> StringType;
```  
  
### <a name="remarks"></a>Примечания  
 **TCharType** является тип знаков, используемых для определения шаблона класса.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы общих библиотек ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)



