---
title: "/ALLOWISOLATION (поиск манифеста) | Microsoft Docs"
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
  - "/ALLOWISOLATION"
  - "VC.Project.VCLinkerTool.AllowIsolation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWISOLATION - параметр компоновщика"
  - "-ALLOWISOLATION - параметр компоновщика"
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ALLOWISOLATION (поиск манифеста)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает поведение нахождения файлов манифеста.  
  
## Синтаксис  
  
```  
/ALLOWISOLATION[:NO]  
```  
  
## Заметки  
 **\/ALLOWISOLATION:NO** указывает на то, что библиотеки DLL загружаются точно так же, как и в отсутствие манифеста; и инициирует установку компоновщиком флага `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` в поле необязательного заголовка `DllCharacteristics`.  
  
 **\/ALLOWISOLATION** инициирует поиск и загрузку манифестов операционной системой.  
  
 Тип **\/ALLOWISOLATION** используется по умолчанию.  
  
 Если параметр изоляции для исполняемого файла отключен, загрузчик Windows не будет пытаться обнаружить манифест приложения для нового процесса.  Новый процесс имеет контекст активации по умолчанию, даже если манифест внутри исполняемого файла, или в том же каталоге, что и исполняемый файл с именем *executable\-name***.exe.manifest**.  
  
 Дополнительные сведения см. в разделе [Manifest Files Reference](http://msdn.microsoft.com/library/aa375632).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните узел **Компоновщик**.  
  
4.  Выберите страницу свойств **Файл манифеста**.  
  
5.  Измените значение свойства **Разрешить изоляцию**.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)