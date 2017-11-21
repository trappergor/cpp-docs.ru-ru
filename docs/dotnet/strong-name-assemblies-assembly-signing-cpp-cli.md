---
title: "Сборки со строгими именами (подписывание сборок) (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 32a9502bbb1143e23ee542c1d9fff593925c527a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>Сборки со строгими именами (подписывание сборок) (C++/CLI)
В этом разделе описывается, как можно подписать сборку, часто называют присвоении сборке строгого имени.  
  
## <a name="remarks"></a>Примечания  
 При использовании Visual C++, используйте параметры компоновщика сборки, чтобы избежать проблем, связанных с атрибуты среды CLR для подписи сборки.  
  
-   <xref:System.Reflection.AssemblyDelaySignAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyFileAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 Причины не с помощью атрибутов: тот факт, что имя ключа является видимым в метаданных сборки, которые могут представлять угрозу безопасности, если имя файла содержит конфиденциальную информацию. Кроме того процесс построения, используемого в среде разработки Visual C++ сделает ключ, с помощью которого подписана сборка, если использовать атрибуты среды CLR для создания строгого имени сборки, а затем запустите средство завершающей обработки, такое как mt.exe на сборку.  
  
 Если построение из командной строки, используются параметры компоновщика подписать сборку и запустите средство завершающей обработки (например, mt.exe), необходимо будет заново подписать сборку sn.exe. Кроме того можно создать и подпись сборки и после запуска средства завершающей обработки, завершив подписание.  
  
 Если при построении в среде разработки используются атрибуты подписи, сборку можно с успехом подписать путем явного вызова sn.exe ([Sn.exe (средство строгих имен)](/dotnet/framework/tools/sn-exe-strong-name-tool)) в событие после построения. Дополнительные сведения см. в разделе [Указание событий сборки](../ide/specifying-build-events.md). Построение может занять меньше времени при использовании атрибутов и события после построения, по сравнению с использованием параметров компоновщика.  
  
 Следующие параметры компоновщика поддерживают подписывание сборок:  
  
-   [/ DELAYSIGN (частичное подписание сборки)](../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/ KEYFILE (указать ключ или пару ключей для подписи сборки)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/ KEYCONTAINER (задание контейнера ключей для подписи сборки)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Дополнительные сведения о строгих сборках см. в разделе [Создание и использование сборок](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies).  
  
## <a name="see-also"></a>См. также  
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)