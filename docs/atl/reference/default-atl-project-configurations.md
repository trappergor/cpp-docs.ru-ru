---
title: "Конфигурации проекта ATL по умолчанию | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, default configurations
ms.assetid: 7e272722-41af-4330-b965-a6d74ec16880
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 41ab65c411bef478d063e5165d3167f58ace37d7
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="default-atl-project-configurations"></a>Конфигурации проекта ATL по умолчанию
В этом разделе сравнивается ATL конфигурации проектов по умолчанию в Visual C++ .NET с помощью конфигурации проектов по умолчанию в Visual C++ 6.0.  
  
## <a name="visual-c-net-default-configurations"></a>Конфигурации по умолчанию Visual C++ .NET  
 В Visual C++ .NET мастер проектов ATL по умолчанию создает два варианта конфигурации проекта.  
  
### <a name="visual-c-net-configurations"></a>Visual C++ .NET конфигураций  
  
|Конфигурация|Набор знаков|Использование ATL|  
|-------------------|-------------------|----------------|  
|Release|MBCS|DLL|  
|Отладка|MBCS|DLL|  
  
 **Набор символов**, **использование ATL** и все изменения в **параметры проекта** диалоговом окне под **Общие** вкладки. Можно также добавить собственные конфигурации с помощью Configuration Manager. Дополнительные сведения см. в разделе [конфигураций построения](/visualstudio/ide/understanding-build-configurations).  
  
## <a name="version-60-default-configurations"></a>Конфигурации по умолчанию в версии 6.0  
 В Visual C++ версии 6.0 мастер приложений COM ATL (теперь называется ATL Project Wizard) создается шесть конфигураций для проекта по умолчанию. Конфигурации не были вариации на выпуск, отладки, Юникода и параметры CRT и ATL для использования. Эти конфигурации могут дублироваться в Visual C++ .NET с помощью Configuration Manager, при желании.  
  
### <a name="version-60-configurations"></a>Конфигурации в версии 6.0  
  
|Конфигурация|Набор знаков|Использование ATL|  
|-------------------|-------------------|----------------|  
|Отладка|MBCS|Static|  
|Отладка Юникода|ЮНИКОД|Static|  
|Выпуск Min зависимостей|MBCS|Static|  
|Выпуск Min зависимостей Юникода|ЮНИКОД|Static|  
|Размер выпуска мин.|MBCS|DLL|  
|Размер Юникода версии мин.|ЮНИКОД|DLL|  
  
## <a name="see-also"></a>См. также  
 [Программирование с использованием ATL и кода времени выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Работа со свойствами проекта](../../ide/working-with-project-properties.md)   
 [Диалоговое окно диспетчера конфигурации](http://msdn.microsoft.com/en-us/fa182dca-282e-4ae5-bf37-e155344ca18b)   
 [Компилирование и сборка](/visualstudio/ide/compiling-and-building-in-visual-studio)


