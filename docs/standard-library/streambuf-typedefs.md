---
title: "Определения типов &lt;streambuf&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 932b5ce7a664f75eb92f19fdbf32363b9300fb09
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

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




