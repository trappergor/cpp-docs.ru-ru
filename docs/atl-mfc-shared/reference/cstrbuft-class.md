---
title: Класс CStrBufT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
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
ms.workload:
- cplusplus
ms.openlocfilehash: 8df7f6c1dbd9987a9f83ed5b33a4c97fd90fec7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cstrbuft-class"></a>Класс CStrBufT
Этот класс предоставляет очистку ресурсов, автоматическое для `GetBuffer` и `ReleaseBuffer` вызывает на существующем `CStringT` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename TCharType>
class CStrBufT
```  
  
#### <a name="parameters"></a>Параметры  
 *TCharType*  
 Тип символа для `CStrBufT` класса. Ниже указаны доступные значения.  
  
- `char`(для символьных строк ANSI)  
  
- `wchar_t`(для символьные строки в Юникоде)  
  
- **TCHAR** (для символьных строк ANSI или Юникод)  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`PCXSTR`|Указатель на строковую константу.|  
|`PXSTR`|Указатель на строку.|  
|`StringType`|Тип строки которого буфера управляться специализации шаблона класса.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CStrBufT::CStrBufT](#cstrbuft)|Конструктор объекта буфера строки.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CStrBufT::SetLength](#setlength)|Задает длину буфера символ объекта связанные строки.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CStrBufT::operator PCXSTR](#operator_pcxstr)|Извлекает **const** указатель на буфер символов объекта связанные строки.|  
|[CStrBufT::operator PXSTR](#operator_pxstr)|Извлекает указатель на буфер символов объекта связанные строки.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание:|  
|----------|-----------------|  
|[CStrBufT::AUTO_LENGTH](#auto_length)|Автоматически определите новую длину строки после выпуска.|  
|[CStrBufT::SET_LENGTH](#set_length)|Задайте длину строкового объекта во время GetBuffer|  
  
## <a name="remarks"></a>Примечания  
 Этот класс используется как класс-оболочку для замены вызовов [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) и [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer), или [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) и `ReleaseBuffer`.  
  
 Разрабатывалась в качестве вспомогательного класса `CStrBufT` обеспечивает удобный способ работы с буфер символов строкового объекта, не беспокоясь о том, как разработчик или когда вызывать `ReleaseBuffer`. Это можно сделать, так как объект-оболочка выходит за пределы области естественным образом в случае исключения или несколько существующих путей кода; приводит к его деструктор для освобождения строкового ресурса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpstr.h  
  
##  <a name="auto_length"></a>CStrBufT::AUTO_LENGTH  
 Автоматически определите новую длину строки после выпуска.  
  
```
static const DWORD AUTO_LENGTH = 0x01;
```  
  
### <a name="remarks"></a>Примечания  
 Автоматически определите новую длину строки после выпуска. Строка должна быть нулем.  
  
##  <a name="cstrbuft"></a>CStrBufT::CStrBufT  
 Создает объект буфера.  
  
```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Строковый объект, связанный с буфером. Как правило, разработчик будет использовать стандартные определения типов для **CStrBuf** ( **TCHAR** вариант), **CStrBufA** ( `char` вариант) и **CStrBufW**  ( `wchar_t` вариант).  
  
 *nMinLength*  
 Минимальная длина буфер символов.  
  
 `dwFlags`  
 Определяет, если длина строки определяется автоматически. Ниже указаны доступные значения.  
  
- **AUTO_LENGTH** длина строки составляет автоматически определяется при [CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) вызывается. Строка должна быть нулем. Значение по умолчанию.  
  
- **SET_LENGTH** длина строки задается [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) вызывается.  
  
### <a name="remarks"></a>Примечания  
 Создает строковый буфер для связанной строки объекта. Во время построения [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) или [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) вызывается.  
  
 Обратите внимание, что конструктор копии `private`.  
  
##  <a name="operator_pcxstr"></a>CStrBufT::operator PCXSTR  
 Прямой доступ к символов, хранящихся в объекте связанной строки как строка C-стиле.  
  
```  
operator PCXSTR() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Символ указатель строки данных.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает указатель на буфер символов строкового объекта. Содержимое объекта string не может изменяться этого указателя.  
  
##  <a name="operator_pxstr"></a>CStrBufT::operator PXSTR  
 Прямой доступ к символов, хранящихся в объекте связанной строки как строка C-стиле.  
  
```
operator PXSTR() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Символ указатель строки данных.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает указатель на буфер символов строкового объекта. Разработчик может изменять содержимое объекта string этого указателя.  
  
##  <a name="pcxstr"></a>CStrBufT::PCXSTR  
 Указатель на строковую константу.  
  
```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```  
  
##  <a name="pxstr"></a>CStrBufT::PXSTR  
 Указатель на строку.  
  
```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```  
  
##  <a name="set_length"></a>CStrBufT::SET_LENGTH  
 Задайте длину строкового объекта в `GetBuffer` времени.  
  
```
static const DWORD SET_LENGTH = 0x02;
```  
  
### <a name="remarks"></a>Примечания  
 Задайте длину строкового объекта во время GetBuffer.  
  
 Определяет, если [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) и [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) вызываются, когда создается объект буфера строки.  
  
##  <a name="setlength"></a>CStrBufT::SetLength  
 Задает длину буфера знаков.  
  
```
void SetLength(int nLength);
```  
  
### <a name="parameters"></a>Параметры  
 `nLength`  
 Новая длина буфера символ объекта строки.  
  
> [!NOTE]
>  Должно быть меньше или равно минимальное буфера длины, указанной в конструкторе `CStrBufT`.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию для задания длины строки, представленный объектом буфера.  
  
##  <a name="stringtype"></a>CStrBufT::StringType  
 Тип строки которого буфера управляться специализации шаблона класса.  
  
```
typedef CSimpleStringT<TCharType> StringType;
```  
  
### <a name="remarks"></a>Примечания  
 **TCharType** символьный тип, используемый для специализации шаблона класса.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)


