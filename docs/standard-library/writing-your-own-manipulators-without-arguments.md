---
title: "Создание собственных манипуляторов без аргументов | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 276bba3dd5ce5debd926ebbc4ccfaf52c6b92097
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="writing-your-own-manipulators-without-arguments"></a>Создание собственных манипуляторов без аргументов
Для создания манипуляторов, которые не имеют аргументов, не требуются ни сложные макросы, ни создание производного класса. Предположим, на принтер нужно передать пару символов \<ESC>[ для перехода в режим полужирного текста. Эту пару символов можно вставить прямо в поток:  
  
```  
cout <<"regular " <<'\033' <<'[' <<"boldface" <<endl;  
```  
  
 Или можно определить манипулятор `bold`, который вставляет символы:  
  
```  
ostream& bold(ostream& os) {  
    return os <<'\033' <<'[';  
}  
cout <<"regular " <<bold <<"boldface" <<endl;  
```  
  
 Глобально определенная функция `bold` принимает ссылку `ostream` в качестве аргумента и возвращает ссылку `ostream`. Это не функция-член и не дружественная функция, так как ей не требуется доступ к закрытым элементам класса. Функция `bold` подключается к потоку, так как оператор потока `<<` перегружен, чтобы принимать этот тип функции. Для этого используется следующее объявление:  
  
```  
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))  
{     // call ios_base manipulator  
 (*_Pfn)(*(ios_base *)this);

    return (*this);

}  
```  
  
 Эту функцию можно использовать для расширения других перегруженных операторов. В данном случае вставка символов `bold` в поток является случайной. Функция вызывается, когда манипулятор вставляется в поток, это не обязательно происходит в момент печати соседних символов. Таким образом печать может быть отложена из-за буферизации потока.  
  
## <a name="see-also"></a>См. также  
 [Потоки вывода](../standard-library/output-streams.md)


