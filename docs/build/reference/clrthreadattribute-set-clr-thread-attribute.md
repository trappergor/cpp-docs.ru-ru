---
title: "-CLRTHREADATTRIBUTE (установите атрибут потока CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.CLRThreadAttribute
dev_langs: C++
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1aae2dadc2fa7a8c9dc67780bb88b4da60d256e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE (Установка атрибута потока среды CLR)
Явно задавать атрибут потока для точки входа CLR-программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}  
```  
  
#### <a name="parameters"></a>Параметры  
 MTA  
 Применяет атрибут MTAThreadAttribute к точке входа программы.  
  
 НЕТ  
 То же, как не указано /CLRTHREADATTRIBUTE.  Позволяет Common Language Runtime (CLR) задайте атрибут потока по умолчанию.  
  
 STA  
 Применяет атрибут STAThreadAttribute к точке входа программы.  
  
## <a name="remarks"></a>Примечания  
 Установка атрибута потока допустим только при построении .exe, поскольку она влияет на точку входа для основного потока.  
  
 При использовании точкой входа по умолчанию (основной или wmain, например) указать потоковой модели с помощью /CLRTHREADATTRIBUTE или поместив работа с потоками (STAThreadAttribute или MTAThreadAttribute) для атрибута функцию входа по умолчанию.  
  
 При использовании точки входа не по умолчанию, укажите потоковой модели при помощи /CLRTHREADATTRIBUTE или поместив threading атрибут функцию входа не по умолчанию, а затем укажите точку входа не по умолчанию с [/Entry](../../build/reference/entry-entry-point-symbol.md) .  
  
 Если потоковая модель, указанная в исходном коде, не совпадает с потоковая модель, указанная с /CLRTHREADATTRIBUTE, компоновщик будет игнорировать атрибут/CLRTHREADATTRIBUTE и примените потоковая модель, указанная в исходном коде.  
  
 Он будет необходимо использовать однопоточную, например, если COM-объект, который использует однопоточную размещаются CLR-программы.  Если CLR-программа использует многопоточную, COM-объект, который использует однопоточную невозможно разместить.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **Дополнительно** страницу свойств.  
  
5.  Изменить **атрибут потока CLR** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)