---
title: "Функции &lt;istream&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: aa35f177bcb986e141d0e46e48dc007a96f94498
ms.lasthandoff: 02/24/2017

---
# <a name="ltistreamgt-functions"></a>Функции &lt;istream&gt;
|||  
|-|-|  
|[swap](#istream_swap)|[ws](#ws)|  
  
##  <a name="istream_swap"></a>  swap  
 Меняет местами элементы двух объектов-потоков.  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_istream<Elem, Tr>& left,  
    basic_istream<Elem, Tr>& right);

template <class Elem, class Tr>  
void swap(
    basic_iostream<Elem, Tr>& left,  
    basic_iostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Поток.  
  
 `right`  
 Поток.  
  
##  <a name="ws"></a>  ws  
 Пропускает пробелы в потоке.  
  
```  
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```  
  
### <a name="parameters"></a>Параметры  
 `_Istr`  
 Поток.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток.  
  
### <a name="remarks"></a>Примечания  
 Манипулятор извлекает и отбрасывает все элементы `ch`, для которого [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)< **ctype**\< **Elem**> >( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). **is**( **ctype**\< **Elem**>:: **space**, **ch**) имеет значение true.  
  
 Функция вызывает [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **eofbit**) при обнаружении конца файла при извлечении элементов. Он возвращает `_Istr`.  
  
### <a name="example"></a>Пример  
  См. раздел [оператор>>](../standard-library/istream-operators.md#operator_gt__gt_) с примером использования `ws`.  
  
## <a name="see-also"></a>См. также  
 [\<istream>](../standard-library/istream.md)


