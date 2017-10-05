---
title: "Определение встроенных функций C++ с использованием dllexport и dllimport | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- inline functions [C++], defining
- functions [C++], defining inline
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
ms.assetid: 3b48678b-e7b8-4eda-bb46-b5d34dcf7817
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 2ad988cc0159030de3746945473f0bbc4eeac296
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>Определение встроенных функций C++ с помощью dllexport и dllimport
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Функцию с атрибутом `dllexport` можно определить как встроенную. В этом случае всегда создается экземпляр функции и она экспортируется независимо от того, ссылается ли на нее какой-либо модуль в программе. Предполагается, что функция должна импортироваться другой программой.  
  
 В качестве встроенной можно также определить функцию, объявленную с атрибутом **dllimport**. В этом случае функцию можно расширить (согласно спецификациям /Ob), но ее экземпляр никогда не создается. В частности, если принимается адрес встроенной импортированной функции, возвращается адрес функции, находящейся в библиотеке DLL. Это поведение аналогично получению адреса невстроенной импортированной функции.  
  
 Эти правила применяются для встроенных функций, определения которых отображаются внутри определения класса. Кроме того, локальные статические данные и строки во встроенных функциях поддерживают одинаковые идентификаторы между библиотекой DLL и клиентом так, как это было бы в одной программе (т. е. исполняемый файл без интерфейса DLL).  
  
 При предоставлении импортированных встроенных функций соблюдайте осторожность. Например, при обновлении библиотеки DLL не следует предполагать, что клиент использует ее измененную версию. Чтобы убедиться в загрузке правильной версии библиотеки DLL, перестройте также клиент этой библиотеки.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)
