---
title: "Аргументы функции main | Документация Майкрософт"
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
ms.assetid: 39824fef-05ad-461d-ae82-49447dda8060
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cff2cb402da87cf37d2f63350088ce4256f3b44c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="arguments-to-main"></a>Аргументы функции main
**ANSI 2.1.2.2.1**Семантика аргументов функции main  
  
 В языке Microsoft C функция, вызываемая при запуске программы, называется **main**. Для функции **main** не существует объявляемого прототипа и она может быть определена с двумя, тремя параметрами или без параметров.  
  
```  
int main( void )  
int main( int argc, char *argv[] )  
int main( int argc, char *argv[], char *envp[] )  
```  
  
 Третья строка приведенного выше примера, где функция **main** принимает три параметра, представляет собой расширение Майкрософт для стандарта ANSI C. Третий параметр (**envp**) — это массив указателей на переменные среды. Массив **envp** завершается пустым указателем. Дополнительные сведения о функции **main** и параметре **envp** см. в статье [main Function and Program Execution](../c-language/main-function-and-program-execution.md) (Функция main и выполнение программы).  
  
 Переменная **argc** никогда не принимает отрицательное значение.  
  
 Массив строк заканчивается переменной **argv[argc]**, содержащей пустой указатель.  
  
 Все элементы массива **argv** являются указателями на строки.  
  
 Программа, вызванная без аргументов командной строки, будет получать для переменной **argc** значение 1, так как имя исполняемого файла размещается в переменной **argv[0]**. (В версиях MS-DOS до 3.0 имя исполняемого файла недоступно. В переменной **argv[0]** размещается буква "C"). Строки, на которые указывают переменные от **argv[1]** до **argv[argc – 1]**, представляют параметры программы.  
  
 Параметры **argc** и **argv** можно изменять. При этом они сохраняют свои последние значения от момента запуска до завершения программы.  
  
## <a name="see-also"></a>См. также  
 [Среда](../c-language/environment.md)