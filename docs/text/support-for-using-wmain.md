---
title: "Поддержка использования wmain | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: wWinMain
dev_langs: C++
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 721915ca5ebbc75b17771dae0804e94aa360177c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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