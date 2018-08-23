---
title: Поддержка использования wmain | Документация Майкрософт
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b82c233d1f03ae4679a355b6782bb9e7dd9dad15
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604067"
---
# <a name="support-for-using-wmain"></a>Поддержка использования wmain
Visual C++ поддерживает определение **wmain** функция и передачи аргументов расширенных символов в Юникоде приложения. Формальные параметры для **wmain**, используя формат, аналогичный `main`. Затем можно передать в качестве аргументов "широкие" символы и указатель среды кодировки Юникод (необязательно) в программу. Параметры `argv` и `envp` для функции **wmain** относятся к типу `wchar_t*`. Пример:  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  В приложениях MFC Юникод используется `wWinMain` как точку входа. В этом случае `CWinApp::m_lpCmdLine` строка в Юникоде. Не забудьте задать `wWinMainCRTStartup` с [/Entry](../build/reference/entry-entry-point-symbol.md) параметр компоновщика.  
  
 Если программа использует `main` функция, среда многобайтовой кодировки создается библиотекой времени выполнения при запуске программы. Копия среды для Юникода создается только при необходимости (например, для вызова функции `_wgetenv` или `_wputenv`). При первом вызове для `_wputenv`, или при первом вызове `_wgetenv` создается, если среда многобайтовой Кодировки уже существует, создается соответствующая среда широкосимвольной строки. Среды затем указывает `_wenviron` глобальной переменной, которая является версией Юникода из `_environ` глобальной переменной. На этом этапе две копии среды (многобайтовой Кодировки и Юникода) существуют одновременно и обслуживаются системой времени выполнения на протяжении всего срока жизни программы.  
  
 Аналогичным образом, если программа использует функцию **wmain**, при запуске программы создается окружение расширенных символов и ссылка на него сохраняется в глобальной переменной `_wenviron`. При первом вызове создается среда MBCS (ASCII) `_putenv` или `getenv` и указывает `_environ` глобальной переменной.  
  
## <a name="see-also"></a>См. также  
 [Поддержка Юникода](../text/support-for-unicode.md)   
 [Общие сведения о программировании Юникода](../text/unicode-programming-summary.md)   
 [Функция WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)