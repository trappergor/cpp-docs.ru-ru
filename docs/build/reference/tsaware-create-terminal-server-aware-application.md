---
title: -TSAWARE (Создание приложения, поддерживающего сервер терминалов) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /tsaware
- VC.Project.VCLinkerTool.TerminalServerAware
dev_langs:
- C++
helpviewer_keywords:
- Terminal Server
- /TSAWARE linker option
- Terminal Server, Terminal Server-aware applications
- -TSAWARE linker option
- TSAWARE linker option
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9caf6c9a47a667b57220b6bf577080d3548e94e9
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198554"
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE (создание приложения, поддерживающего сервер терминалов)
```  
/TSAWARE[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр/TSAWARE устанавливает флаг в поле IMAGE_OPTIONAL_HEADER DllCharacteristics в необязательном заголовке образа программы. Если этот флаг установлен, сервер терминалов не будет вносить определенные изменения в приложение.  
  
 Если приложение не поддерживает сервер терминалов (также известный как приложение прежних версий), сервер терминалов выполняет определенные изменения в приложении, чтобы оно работало должным образом в многопользовательской среде. Например сервер терминалов создаст виртуальную папку Windows, таким образом, что каждый пользователь получит в папку Windows, вместо получения directory системы Windows. Это предоставляет пользователям доступ к собственным файлам INI. Кроме того сервер терминалов вносит ряд изменений в реестр приложения прежних версий. Эти изменения снижают скорость загрузки устаревшее приложение на сервере терминалов.  
  
 Если приложение поддерживает сервер терминалов, он должен полагаться на ini-файлы и не записи **HKEY_CURRENT_USER** реестра во время установки.  
  
 При использовании/TSAWARE, и приложение по-прежнему использует ini-файлы, файлы будут совместно использоваться всеми пользователями системы. Если допустима, по-прежнему можно связать приложение с/TSAWARE; в противном случае необходимо использовать: No.  
  
 Параметр/TSAWARE включена по умолчанию для Windows и консольных приложений. См. в разделе [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) и [/Version](../../build/reference/version-version-information.md) сведения.  
  
 / TSAWARE не является допустимым для драйверов, VxD или DLL.  
  
 Если приложение было скомпоновано с/TSAWARE, DUMPBIN [/Headers](../../build/reference/headers.md) будут отображаться сведения об этом.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **системы** страницу свойств.  
  
4.  Изменить **сервера терминалов** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Хранить сведения о пользователе](/windows/desktop/TermServ/storing-user-specific-information)   
 [Устаревшие приложения в среде служб терминалов](https://msdn.microsoft.com/library/aa382957.aspx)