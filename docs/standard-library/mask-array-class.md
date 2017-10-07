---
title: "Класс mask_array | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- valarray/std::mask_array
dev_langs:
- C++
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 882091956f9d9c5985e3bfacfe015ff81e84ac6c
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="maskarray-class"></a>Класс mask_array
Внутренний, вспомогательный класс шаблона, который поддерживает объекты, представляющие подмножества родительских valarray, указанных логическим выражением, предоставляя операции между массивами подмножеств.  
  
## <a name="syntax"></a>Синтаксис  
  
  
  
## <a name="remarks"></a>Примечания  
 Класс описывает объект, который хранит ссылку на объект **va** класса [valarray](../standard-library/valarray-class.md)**\<Type>**, вместе с объектом **ba** класса [valarray\<bool>](../standard-library/valarray-bool-class.md), который описывает последовательность элементов для выбора из объекта **valarray\<Type>**.  
  
 Объект **mask_array\<Type>** создается только путем написания выражения вида [va&#91;ba&#93;](../standard-library/valarray-class.md#op_at). После этого функции-члены класса mask_array ведут себя как соответствующие сигнатуры функций, заданные для **valarray\<Type>** с той разницей, что затрагивается только последовательность выбранных элементов.  
  
 Последовательность состоит максимум из **ba.size** элементов. Элемент *J* включается, только если **ba**[ *J*] имеет значение true. Таким образом, в последовательности существует столько элементов, сколько существует элементов со значением true в **ba**. Если `I` является индексом наименьшего элемента true в **ba**, то **va**[ `I`] является нулевым элементом в выбранной последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// mask_array.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      va [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      va [ i ] =  -1;  
  
   cout << "The initial operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   // Use masked subsets to assign a value of 10  
   // to all elements grrater than 3 in value  
   va [va > 3 ] = 10;  
   cout << "The modified operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
}  
```  
  
### <a name="output"></a>Вывод  
  
```  
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).  
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<valarray>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


