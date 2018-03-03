---
title: "-Zo (улучшение оптимизированного процесса отладки) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- -Zo
- /Zo
dev_langs:
- C++
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 326bd1c6c435dec97c309014dfc81ca444cc5eb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo (улучшение оптимизированного процесса отладки)
Создает расширенные сведения об отладке для оптимизированного кода в неотладочных сборках.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
/Zo[-]  
```  
  
## <a name="remarks"></a>Примечания  
 **/Zo** переключатель компилятора создает расширенные сведения об отладке для оптимизированного кода. При оптимизации могут использоваться регистраторы для локальных переменных, изменения в порядке кода, векторизация циклов и вызовы встраиваемых функций. Такая оптимизация может скрывать связи между исходным кодом и кодом скомпилированного объекта. **/Zo** — указывает компилятору создавать дополнительные сведения об отладке для локальных переменных и встроенных функций. Используйте его для просмотра переменных в **видимые**, **локальные**, и **Контрольные значения** windows при пошаговом прохождении оптимизированного кода в отладчике Visual Studio. Он также позволяет выполнять трассировки стека для отображения встроенных функций в отладчике WinDBG. Отладочные построения с отключенной оптимизацией ([/Od](../../build/reference/od-disable-debug.md)) не требуется дополнительных сведений об отладке при **/Zo** указано. Используйте **/Zo** коммутатора для отладки конфигураций выпуска с включенной оптимизацией. Дополнительные сведения о переключателях оптимизации см. в разделе [параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md). **/Zo** параметр включен по умолчанию в Visual Studio, при указании отладочной информации с **/ZI** или **/Z7**. Укажите **/Zo-** явно отключить этот параметр компилятора.  
  
 **/Zo** коммутатор доступен, начиная с Visual Studio 2013 с обновлением 3, и он заменяет не документированный ранее **/d2Zi+** переключения.  
  
### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>Установка параметра компилятора /Zo в Visual Studio  
  
1.  Откройте **страницы свойств** диалоговое окно для проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **свойства конфигурации**, **C/C++** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Изменить **Дополнительные параметры** включив `/Zo` и выберите **ОК**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)   
 [/ Z7, / Zi, /ZI (формат отладочной информации)](../../build/reference/z7-zi-zi-debug-information-format.md)   
 [Изменить и продолжить](/visualstudio/debugger/edit-and-continue)