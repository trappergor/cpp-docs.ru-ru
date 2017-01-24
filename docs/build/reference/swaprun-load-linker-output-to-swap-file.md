---
title: "/SWAPRUN (загрузка выходных данных компоновщика в файл подкачки) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.SwapRunFromNet"
  - "/swaprun"
  - "VC.Project.VCLinkerTool.SwapRunFromCD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SWAPRUN - параметр компоновщика"
  - "файлы [C++], LINK"
  - "LINK - средство [C++], результат"
  - "компоновщик [C++], копирование вывода в файл подкачки"
  - "выходные файлы, компоновщик"
  - "файл подкачки для вывода компоновщика"
  - "SWAPRUN - параметр компоновщика"
  - "-SWAPRUN - параметр компоновщика"
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SWAPRUN (загрузка выходных данных компоновщика в файл подкачки)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SWAPRUN:{NET|CD}  
```  
  
## Заметки  
 Параметр \/SWAPRUN предписывает операционной системе сначала копировать выходные данные компоновщика в файл подкачки, а затем запускать образ оттуда.  Эта функция поддерживается операционной системой Windows NT 4.0 \(и более поздних версий\).  
  
 Если задан параметр NET, операционная система сначала копирует двоичный образ в файл подкачки и запускает его оттуда.  Этот параметр используется для запуска приложений по сети.  Если задан параметр, CD операционная система выполнит копирование образа в файл ресурса страницы на съемный диск, а затем выполнит его загрузку.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Система**.  
  
4.  Измените значение одного из следующих свойств:  
  
    -   **Запуск с компакт\-диска с помощью файла подкачки**  
  
    -   **Запускать из сети с помощью файла подкачки**  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. описание свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)