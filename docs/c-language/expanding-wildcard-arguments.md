---
title: "Расширение аргументов заполнителей | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: b8444a15e8f0fb9a8e4322f1bb2001b19d38eec1
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="expanding-wildcard-arguments"></a>Расширение аргументов заполнителей
**Блок, относящийся только к системам Майкрософт**  
  
 При выполнении программы на языке C можно использовать любой из двух подстановочных знаков, вопрос (?) или звездочку (*), для задания аргументов имени файла и пути в командной строке.  
  
 По умолчанию подстановочные знаки в аргументах командной строки не разворачиваются. Вы можете заменить обычную процедуру загрузки вектора аргументов `argv` на версию, которая разворачивает подстановочные знаки, используя компоновку с файлом setargv.obj или wsetargv.obj. Если программа использует функцию `main` , скомпонуйте ее с файлом setargv.obj. Если программа использует функцию `wmain` , скомпонуйте ее с файлом wsetargv.obj. Они оба реализуют эквивалентное поведение.  
  
 Чтобы скомпоновать программу с файлом setargv.obj или wsetargv.obj, используйте параметр **/link** . Пример:  
  
 **cl example.c /link setargv.obj**  
  
 Подстановочные знаки разворачиваются так же, как команды операционной системы. (См. ознакомительные сведения о подстановочных знаках в руководстве пользователя вашей ОС).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Link Options](../c-runtime-library/link-options.md)  (Параметры ссылок)  
 [Функция main и выполнение программ](../c-language/main-function-and-program-execution.md)
