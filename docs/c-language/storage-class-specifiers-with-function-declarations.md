---
title: "Описатели классов хранения с объявлениями функций | Документация Майкрософт"
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
- function specifiers, storage class
- declaring functions, specifiers
- external declarations
- specifiers, function
- external linkage, function declarations
- external linkage, storage-class specifiers
ms.assetid: 801d7df2-efa9-4924-a725-274a5654cfd4
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 45d4ef74f9ea37167c6467c8025dbf941a9c3be1
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="storage-class-specifiers-with-function-declarations"></a>Спецификаторы классов хранения с объявлениями функций
В объявлениях функций можно использовать описатель класса хранения **static** или `extern`. Функции всегда имеют глобальное время существования.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 Объявления функций на внутреннем уровне имеют то же значение, что и объявления функций на внешнем уровне. Это означает, что функция видна с момента объявления на протяжении всего времени существования записи преобразования, даже если она объявлена с локальной областью видимости.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
 Правила видимости для функций слегка отличаются от правил для переменных следующим.  
  
-   Функция, объявленная как **static**, видна только в пределах файла исходного кода, в котором она определена. Функции в том же файле исходного кода могут вызывать функцию **static**, но функции в других файлах исходного кода не могут получить прямой доступ к ней по имени. Можно объявить другую функцию **static** с тем же именем в другом файле исходного кода, не создавая конфликта.  
  
-   Функции, объявленные как `extern`, видны во всех файлах исходного кода программы (если впоследствии такая функция не будет повторно объявлена как **static**). Любая функция может вызывать функцию `extern`.  
  
-   Объявления функций, опускающие описатель класса хранения, по умолчанию являются `extern`.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 В системах Майкрософт можно повторно определять идентификатор `extern` как **static**.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Классы хранения в C](../c-language/c-storage-classes.md)
