---
title: Поддержка использования wmain | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- wWinMain
dev_langs:
- C++
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8b82b9f13da1b7c4884001fed5afce832147714
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="support-for-using-wmain"></a>Поддержка использования wmain
Visual C++ поддерживает определение **wmain** и передачи аргументов в приложение Юникода. Формальные параметры для **wmain**, используя формат, аналогичный **основной**. Затем можно передать в качестве аргументов "широкие" символы и указатель среды кодировки Юникод (необязательно) в программу. Параметры `argv` и `envp` для функции **wmain** относятся к типу `wchar_t*`. Пример:  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  В приложениях MFC Юникод используется **wWinMain** точкой входа. В этом случае `CWinApp::m_lpCmdLine` строка в Юникоде. Не забудьте задать **wWinMainCRTStartup** с [/Entry](../build/reference/entry-entry-point-symbol.md) компоновщика.  
  
 Если программа использует функцию **main**, окружение многобайтовой кодировки создается библиотекой времени выполнения при запуске программы. Копия среды для Юникода создается только при необходимости (например, для вызова функции `_wgetenv` или `_wputenv`). При первом вызове для `_wputenv`, или при первом вызове для `_wgetenv` Если среда многобайтовой Кодировки уже существует, создается соответствующая среда широкосимвольной строки. Среде затем указывает `_wenviron` глобальной переменной, которая является версия с расширенными символами из `_environ` глобальной переменной. В этот момент две копии среды (многобайтовой Кодировки и Юникода) существуют одновременно и поддерживаются системой времени выполнения в течение всего срока жизни программы.  
  
 Аналогичным образом, если программа использует функцию **wmain**, при запуске программы создается окружение расширенных символов и ссылка на него сохраняется в глобальной переменной `_wenviron`. Среда многобайтовой Кодировки (ASCII) создается при первом вызове для `_putenv` или `getenv` и указывает `_environ` глобальной переменной.  
  
## <a name="see-also"></a>См. также  
 [Поддержка Юникода](../text/support-for-unicode.md)   
 [Общие сведения о программировании Юникода](../text/unicode-programming-summary.md)   
 [Функция WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)