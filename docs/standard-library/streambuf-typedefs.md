---
title: "Определения типов &lt;streambuf&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- streambuf/std::streambuf
- streambuf/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8a11f21fc55babc7c71bb312bc582719f532347a
ms.lasthandoff: 02/24/2017

---
# <a name="ltstreambufgt-typedefs"></a>Определения типов &lt;streambuf&gt;
|||  
|-|-|  
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|  
  
##  <a name="streambuf"></a>  streambuf  
 Специализация `basic_streambuf`, использующая `char` в качестве параметров шаблона.  
  
```
typedef basic_streambuf<char, char_traits<char>> streambuf;
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_streambuf](../standard-library/basic-streambuf-class.md), специализированного для элементов типа `char` с признаками символа по умолчанию.  
  
##  <a name="wstreambuf"></a>  wstreambuf  
 Специализация `basic_streambuf`, использующая `wchar_t` в качестве параметров шаблона.  
  
```
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_streambuf](../standard-library/basic-streambuf-class.md), специализированного для элементов типа `wchar_t` с признаками символа по умолчанию.  
  
## <a name="see-also"></a>См. также  
 [\<streambuf>](../standard-library/streambuf.md)




