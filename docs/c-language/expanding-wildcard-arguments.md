---
title: "Расширение аргументов заполнителей | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f710cc1695579bf1a6f873229c347966888bc745
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="expanding-wildcard-arguments"></a>Расширение аргументов заполнителей
**Блок, относящийся только к системам Microsoft**  
  
 При выполнении программы на языке C можно использовать любой из двух подстановочных знаков, вопрос (?) или звездочку (*), для задания аргументов имени файла и пути в командной строке.  
  
 По умолчанию подстановочные знаки в аргументах командной строки не разворачиваются. Вы можете заменить обычную процедуру загрузки вектора аргументов `argv` на версию, которая разворачивает подстановочные знаки, используя компоновку с файлом setargv.obj или wsetargv.obj. Если программа использует функцию `main` , скомпонуйте ее с файлом setargv.obj. Если программа использует функцию `wmain` , скомпонуйте ее с файлом wsetargv.obj. Они оба реализуют эквивалентное поведение.  
  
 Чтобы скомпоновать программу с файлом setargv.obj или wsetargv.obj, используйте параметр **/link** . Пример:  
  
 **cl example.c /link setargv.obj**  
  
 Подстановочные знаки разворачиваются так же, как команды операционной системы. (См. ознакомительные сведения о подстановочных знаках в руководстве пользователя вашей ОС).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Link Options](../c-runtime-library/link-options.md)  (Параметры ссылок)  
 [Функция main и выполнение программ](../c-language/main-function-and-program-execution.md)