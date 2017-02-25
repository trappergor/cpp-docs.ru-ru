---
title: "Перехват ошибок | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления ActiveX [C++], перехват ошибок"
  - "перехват ошибок [C++]"
ms.assetid: c509b089-a542-44be-8f22-dc5832967a48
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Перехват ошибок
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При выполнении привязки данных перехват ошибок производится посредством событий ошибок и объектов ошибок.  
  
##  <a name="vcreferrortrappingviaerrorevents"></a> Перехват ошибок посредством событий ошибок  
 Как для элемента управления данными ADO, так и для элемента управления данными RemoteData RDO определены события ошибок.  Для события ошибки обычно задается обработчик событий.  Обработчики событий должны иметь следующую сигнатуру:  
  
```  
void CMyDlg::OnErrorAdodc1(long ErrorNumber,  
                           BSTR* FAR Description,  
                           long Scode,  
                           LPCTSTR Source,  
                           LPCTSTR HelpFile,  
                           long HelpContext,  
                           BOOL FAR* fCancelDisplay)  
```  
  
 Как правило, поле Description заполняется, а поля ErrorNumber и Scode заполняются только в случае ошибок COM.  Стандартный обработчик ошибок выводит содержимое поля Description в окне сообщений.  Примеры.  
  
```  
{  
   USES_CONVERSION;     
// note: have to include the ATL file ATLConv.h to use the ATL conversion macros  
   ::AfxMessageBox(OLE2T(*Description), MB_OK);  
}  
```  
  
 Однако, поскольку элемент управления данными ADO и элемент управления RemoteData RDO уже настроены на перехват ошибок, дополнительного кодирования не требуется.  
  
##  <a name="vcreferrortrappingviaerrorobjects"></a> Перехват ошибок посредством объектов ошибок  
 Как в ADO, так и в RDO имеются объекты ошибок.  При создании [классов\-оболочек](../../data/ado-rdo/wrapper-classes.md) элемент управления RDO RemoteData создает оболочки для объектов ошибок. Однако элемент управления данными ADO не создает подобных оболочек.  
  
 Элемент управления данными ADO автоматически выводит сообщения об ошибках ADO.  
  
## См. также  
 [Привязка данных в Visual C\+\+ с помощью элементов управления ActiveX](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)