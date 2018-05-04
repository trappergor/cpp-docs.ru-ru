---
title: 'основной: запуск программы | Документы Microsoft'
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
ms.openlocfilehash: 2999596fe30afca4c9945efc34a8537e9f45e14a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="main-program-startup"></a>Функция main. Запуск программы
Специальная функция с именем `main` является отправной точкой выполнения для всех программ на языках C и C++. При создании кода, который соответствует модели программирования [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)], можно использовать функцию `wmain`, представляющую собой версию функции `main` для расширенных символов.  
  
 Компилятор не предоставляет предварительно определенную функцию `main`. Она должна присутствовать в тексте программы.  
  
 Синтаксис объявления функции `main` выглядит следующим образом:  
  
```  
int main();  
```  
  
 или, если требуется,  
  
```  
int main(int argc, char *argv[], char *envp[]);  
```  
  
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Синтаксис объявления функции `wmain` выглядит следующим образом:  
  
```  
int wmain( );  
```  
  
 или, если требуется,  
  
```  
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);  
```  
  
 Можно также использовать функцию `_tmain`, определенную в файле TCHAR.h. При отсутствии определения _UNICODE функция `_tmain` разрешается в функцию `main`. В противном случае функция `_tmain` разрешается в функцию `wmain`.  
  
 Функции `main` и `wmain` можно также объявлять с возвращаемым значением `void` (без возвращаемого значения). При объявлении `main` или `wmain` как возвращающий `void`, не может вернуть код завершения в родительский процесс или операционную систему с помощью [возвращают](../cpp/return-statement-in-program-termination-cpp.md) инструкции. Возвращает код выхода при `main` или `wmain` объявляется как `void`, необходимо использовать [выхода](../cpp/exit-function.md) функции.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
 Типы для параметров `argc` и `argv` определяются языком. Имена `argc`, `argv` и `envp` являются традиционными, но они не обязательны для компилятора. Дополнительные сведения и пример см. в разделе [определения аргументов](../cpp/argument-definitions.md).  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Использование wmain вместо main](../cpp/using-wmain-instead-of-main.md)   
 [Ограничения функции main](../cpp/main-function-restrictions.md)