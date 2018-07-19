---
title: Функция Exit | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d08ac1375fa383543eaafb5b3ce49cd2bbfbc4da
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941084"
---
# <a name="exit-function"></a>Функция exit
`exit` Функции, объявленные в стандартном включаемом файле \<stdlib.h >, завершает программу C++.  
  
 Значение, указанное в качестве аргумента `exit` возвращается в операционную систему, как ее возвращаемое код или код выхода. Принято, чтобы нулевым кодом возврата обозначалось, что программа завершена успешно.  
  
> [!NOTE]
>  Можно использовать константы, EXIT_FAILURE и EXIT_SUCCESS, определенные в \<stdlib.h >, чтобы указать на успех или сбой программы.  
  
 Выдача **возвращают** инструкции от `main` функция эквивалентно вызову `exit` функции с возвращаемым значением в качестве аргумента.  
  
 Дополнительные сведения см. в разделе [выйти из](../c-runtime-library/reference/exit-exit-exit.md) в *Справочник по библиотеке времени выполнения*.  
  
## <a name="see-also"></a>См. также  
 [Завершение программы](../cpp/program-termination.md)