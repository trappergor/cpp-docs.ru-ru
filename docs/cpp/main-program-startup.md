---
title: 'основной: запуск программы | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- vc.main.startup
- _tmain
dev_langs:
- C++
helpviewer_keywords:
- program startup [C++]
- entry points, program
- wmain function
- _tmain function
- startup code, main function
- main function, program startup
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f78a122837fc2cb9a89083d5be8fd2b488c1772
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939228"
---
# <a name="main-program-startup"></a>Функция main. Запуск программы
Это специальная функция с именем `main` является начальной точкой выполнения для всех программ C и C++. При создании кода, который соответствует модели программирования [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)], можно использовать функцию `wmain`, представляющую собой версию функции `main` для расширенных символов.  
  
 Компилятор не предоставляет предварительно определенную функцию `main`. Она должна присутствовать в тексте программы.  
  
 Синтаксис объявления функции `main` выглядит следующим образом:  
  
```cpp 
int main();  
```  
  
 или, если требуется,  
  
```cpp 
int main(int argc, char *argv[], char *envp[]);  
```  
  
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Синтаксис объявления функции `wmain` выглядит следующим образом:  
  
```cpp 
int wmain( );  
```  
  
 или, если требуется,  
  
```cpp 
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);  
```  
  
 Можно также использовать функцию `_tmain`, определенную в файле TCHAR.h. При отсутствии определения _UNICODE функция `_tmain` разрешается в функцию `main`. В противном случае функция `_tmain` разрешается в функцию `wmain`.  
  
 Кроме того `main` и `wmain` функции могут быть объявлены как возвращающий **void** (без возвращаемого значения). При объявлении `main` или `wmain` как возвращающий **void**, код выхода не может вернуться к родительскому процессу или операционной системы с помощью [возвращают](../cpp/return-statement-in-program-termination-cpp.md) инструкции. Для возврата кода завершения, когда `main` или `wmain` объявляется как **void**, необходимо использовать [выйти из](../cpp/exit-function.md) функции.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
 Типы для параметров `argc` и `argv` определяются языком. Имена `argc`, `argv` и `envp` являются традиционными, но они не обязательны для компилятора. Дополнительные сведения и пример см. в разделе [определения аргументов](../cpp/argument-definitions.md).  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Использование wmain вместо main](../cpp/using-wmain-instead-of-main.md)   
 [Ограничения функции Main](../cpp/main-function-restrictions.md)   
 [Анализ аргументов командной строки C++](../cpp/parsing-cpp-command-line-arguments.md)
