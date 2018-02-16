---
title: "Универсальные приложения Windows (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a293f833de7bc575209089362bcaf146d074684b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="universal-windows-apps-c"></a>Универсальные приложения Windows (C++)
Универсальные приложения для платформы Windows (UWP) реализуют набор принципов разработки, выделяющих простые пользовательские интерфейсы, организованные вокруг содержимого, которое автоматически настраивается в соответствии с различными размерами экранов на разных устройствах. Для создания пользовательского интерфейса используется разметка XAML, а для кода — неуправляемый код C++. Можно также создавать компоненты (DLL), которые могут применяться приложениями UWP, написанными на других языках. Область API для приложений UWP представляет среду выполнения Windows, которая является хорошо организованную библиотеку, которая предоставляет широкий набор служб для операционной системы.  

> [!TIP]  
> Для Windows 10 можно использовать преобразователь приложения рабочего стола упаковка существующего приложения рабочего стола для развертывания с помощью Microsoft Store. Дополнительные сведения см. в статьях [Использование среды выполнения Visual C++ в проекте Centennial](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) и [Перенос классического приложения на универсальную платформу Windows (UWP) с помощью Desktop Bridge](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root).
  
  
## <a name="uwp-apps-that-use-ccx"></a>Приложения UWP, использующие C++/CX  
  
|||  
|-|-|  
|[Справочник по языку Visual C++ (C++/CX)](../cppcx/visual-c-language-reference-c-cx.md)|Описание набора расширений, которые упрощают использование интерфейсов API среды выполнения Windows C++ и обеспечивают обработку ошибок, основанную на исключениях.|  
|[Построение приложений и библиотек (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|Описание создания библиотек DLL и статических библиотек, доступных из приложения или компонента C++/CX.|  
|[Учебник: Создание первого приложения UWP, с помощью C++](https://docs.microsoft.com/en-us/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|Пошаговое руководство, представляющее основные понятия разработки приложений UWP на C++. (Еще не обновлено для разработки UWP на платформе Windows 10).|  
|[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Описание создания библиотек DLL, которые можно использовать в других приложениях UWP и компонентов.|  
|[Разработка игр](https://docs.microsoft.com/en-us/windows/uwp/gaming/)|Описание использования DirectX и C++ для создания игр.|  
  
## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Приложения UWP, использующие библиотека шаблонов C++ среды выполнения Windows (WRL) 
 Библиотека шаблонов C++ среды выполнения Windows предоставляет низкоуровневые интерфейсы COM, с помощью которых код C++ стандарта ISO может обращаться к среды выполнения Windows в среде без поддержки исключений. В большинстве случаев рекомендуется использовать C + +/ CX вместо библиотека шаблонов C++ среды выполнения Windows для разработки приложений UWP. Сведения о библиотека шаблонов C++ среды выполнения Windows см. в разделе [библиотеки шаблонов C++ (WRL) среды выполнения Windows](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
## <a name="see-also"></a>См. также  
 [Visual C++](../visual-cpp-in-visual-studio.md)

