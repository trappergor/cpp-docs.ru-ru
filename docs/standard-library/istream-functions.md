---
title: "Функции &lt;istream&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 049f039f54194e7a1d4c4d1958a1e4cbd50cd76e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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
 Манипулятор извлекает и отбрасывает все элементы `ch`, для которого [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype**\< **Elem**> >( [getloc](../standard-library/ios-base-class.md#getloc)). **is**( **ctype**\< **Elem**>:: **space**, **ch**) имеет значение true.  
  
 Функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) при обнаружении конца файла при извлечении элементов. Он возвращает `_Istr`.  
  
### <a name="example"></a>Пример  
  См. раздел [оператор>>](../standard-library/istream-operators.md#op_gt_gt) с примером использования `ws`.  
  
## <a name="see-also"></a>См. также  
 [\<istream>](../standard-library/istream.md)

