---
title: "Определения типов &lt;istream&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
caps.latest.revision: 10
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: cc53eb1fed0dfc562ddb59ad239d716dd6057ebd
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="ltistreamgt-typedefs"></a>Определения типов &lt;istream&gt;
||||  
|-|-|-|  
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|  
|[wistream](#wistream)|  
  
##  <a name="iostream"></a>  iostream  
 Тип `basic_iostream`, специализированный для `char`.  
  
```  
typedef basic_iostream<char, char_traits<char>> iostream;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_iostream](../standard-library/basic-iostream-class.md), специализированного для элементов типа `char` с признаками символов по умолчанию.  
  
##  <a name="istream"></a>  istream  
 Тип `basic_istream`, специализированный для `char`.  
  
```  
typedef basic_istream<char, char_traits<char>> istream;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_istream](../standard-library/basic-istream-class.md), специализированного для элементов типа `char` с признаками символов по умолчанию.  
  
##  <a name="wiostream"></a>  wiostream  
 Тип `basic_iostream`, специализированный для `wchar_t`.  
  
```  
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_iostream](../standard-library/basic-iostream-class.md), специализированного для элементов типа `wchar_t` с признаками символов по умолчанию.  
  
##  <a name="wistream"></a>  wistream  
 Тип `basic_istream`, специализированный для `wchar_t`.  
  
```  
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_istream](../standard-library/basic-istream-class.md), специализированного для элементов типа `wchar_t` с признаками символов по умолчанию.  
  
## <a name="see-also"></a>См. также  
 [\<istream>](../standard-library/istream.md)


