---
title: Rollenobjekt (TMSL) | Microsoft Docs
ms.custom: 
ms.date: 05/30/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1812f60b-bd5f-417c-96bc-3d834bdb4d3c
caps.latest.revision: 6
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 8073ac6a467673a5781f747c1a8ab60be17f31a3
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="roles-object-tmsl"></a>Rollenobjekt (TMSL)

[!INCLUDE[ssas-appliesto-sql2016-later-aas](../../includes/ssas-appliesto-sql2016-later-aas.md)]

  Definiert eine Rolle für das Modell, das eine Auflistung von Berechtigungen angibt. Mitgliedschaft in Datenbankrolle besteht aus Windows-Sicherheitsprinzipalen. Sie können Filter festlegen, für eine Rolle den Zugriff auf bestimmte Objekte einschränken.  
  
## <a name="object-definition"></a>Objektdefinition  
 Alle Objekte verfügen über einen gemeinsamen Satz von Eigenschaften, einschließlich Name, Typ, Beschreibung, eine eigenschaftsauflistung und Anmerkungen. **Rolle** Objekte verfügen außerdem über die folgenden Eigenschaften.  
  
 modelPermission  
 Stellt einen Bereich von Berechtigungen für eine Datenbank her. Gültige Werte sind none,  
                  Lesen,  
                  ReadRefresh,  
                  Aktualisierung  
                  und Administrator. Finden Sie unter [Rollen und Berechtigungen &#40; Analysis Services &#41; ](../../analysis-services/multidimensional-models/roles-and-permissions-analysis-services.md) Informationen zu Datenbankberechtigungen.  
  
 Mitglieder  
 Mitglieder bestehen aus einem Elementnamen und die ID, wobei Elementname ist der Alias oder ein Anzeigename, der ein Windows-Sicherheitsprinzipal, und die ID ist die Sicherheits-ID. Beide werden in der Funktionsdefinition angegeben. Finden Sie unter [SID Komponenten](https://msdn.microsoft.com/en-us/library/windows/desktop/aa379597\(v=vs.85\).aspx) ausführliche Informationen zu Bezeichnern.  
  
 TablePermissions  
 Eine Table-Berechtigung ist ein benanntes Objekt mit den Berechtigungen, die über einen DAX-Ausdruck definiert. Diese Eigenschaft ist optional, verwendet, um einen Sicherheitsfilter anzuwenden.  
  
## <a name="usage"></a>Verwendung  
 **Rolle** Objekte dienen [Alter-Befehl &#40; TMSL &#41; ](../../analysis-services/tabular-models-scripting-language-commands/alter-command-tmsl.md), [Erstellen Befehl &#40; TMSL &#41; ](../../analysis-services/tabular-models-scripting-language-commands/create-command-tmsl.md), [CreateOrReplace-Befehl &#40; TMSL &#41; ](../../analysis-services/tabular-models-scripting-language-commands/createorreplace-command-tmsl.md), und [Befehl &#40; löschen TMSL &#41; ](../../analysis-services/tabular-models-scripting-language-commands/delete-command-tmsl.md).  
  
 Ein **Rolle** Objekt ist eine Eigenschaft eines Modells, aber es kann auch als Eigenschaft eines Datenbankobjekts ausgehend von der 1: 1-Zuordnung zwischen Modell und Datenbank angegeben werden.  
  
 Beim Erstellen, ersetzen oder ändern ein Role-Objekt, geben Sie alle Lese-/ Schreibzugriff Eigenschaften der Objektdefinition. Eine Lese-/ Schreibzugriff-Eigenschaft nicht angegeben, gilt einen Löschvorgang.  
  
## <a name="full-syntax"></a>Gesamte Syntax  
 Im folgenden ist die schemendarstellung eines Role-Objekts eines Modells.  
  
```  
"roles": {  
          "type": "array",  
          "items": {  
            "description": "ModelRole object of Tabular Object Model (TOM)",  
            "type": "object",  
            "properties": {  
              "name": {  
                "type": "string"  
              },  
              "description": {  
                "anyOf": [  
                  {  
                    "type": "string"  
                  },  
                  {  
                    "type": "array",  
                    "items": {  
                      "type": "string"  
                    }  
                  }  
                ]  
              },  
              "modelPermission": {  
                "enum": [  
                  "none",  
                  "read",  
                  "readRefresh",  
                  "refresh",  
                  "administrator"  
                ]  
              },  
              "annotations": {  
                "type": "array",  
                "items": {  
                  "description": "Annotation object of Tabular Object Model (TOM)",  
                  "type": "object",  
                  "properties": {  
                    "name": {  
                      "type": "string"  
                    },  
                    "value": {  
                      "anyOf": [  
                        {  
                          "type": "string"  
                        },  
                        {  
                          "type": "array",  
                          "items": {  
                            "type": "string"  
                          }  
                        }  
                      ]  
                    }  
                  },  
                  "additionalProperties": false  
                }  
              },  
              "members": {  
                "type": "array",  
                "items": {  
                  "anyOf": [  
                    {  
                      "description": "WindowsModelRoleMember object of Tabular Object Model (TOM)",  
                      "type": "object",  
                      "properties": {  
                        "memberName": {  
                          "type": "string"  
                        },  
                        "memberId": {  
                          "type": "string"  
                        },  
                        "annotations": {  
                          "type": "array",  
                          "items": {  
                            "description": "Annotation object of Tabular Object Model (TOM)",  
                            "type": "object",  
                            "properties": {  
                              "name": {  
                                "type": "string"  
                              },  
                              "value": {  
                                "anyOf": [  
                                  {  
                                    "type": "string"  
                                  },  
                                  {  
                                    "type": "array",  
                                    "items": {  
                                      "type": "string"  
                                    }  
                                  }  
                                ]  
                              }  
                            },  
                            "additionalProperties": false  
                          }  
                        }  
                      },  
                      "additionalProperties": false  
                    },  
                    {  
                      "description": "ExternalModelRoleMember object of Tabular Object Model (TOM)",  
                      "type": "object",  
                      "properties": {  
                        "memberName": {  
                          "type": "string"  
                        },  
                        "memberId": {  
                          "type": "string"  
                        },  
                        "identityProvider": {  
                          "type": "string"  
                        },  
                        "memberType": {  
                          "enum": [  
                            "auto",  
                            "user",  
                            "group"  
                          ]  
                        },  
                        "annotations": {  
                          "type": "array",  
                          "items": {  
                            "description": "Annotation object of Tabular Object Model (TOM)",  
                            "type": "object",  
                            "properties": {  
                              "name": {  
                                "type": "string"  
                              },  
                              "value": {  
                                "anyOf": [  
                                  {  
                                    "type": "string"  
                                  },  
                                  {  
                                    "type": "array",  
                                    "items": {  
                                      "type": "string"  
                                    }  
                                  }  
                                ]  
                              }  
                            },  
                            "additionalProperties": false  
                          }  
                        }  
                      },  
                      "additionalProperties": false  
                    }  
                  ]  
                }  
              },  
              "tablePermissions": {  
                "type": "array",  
                "items": {  
                  "description": "TablePermission object of Tabular Object Model (TOM)",  
                  "type": "object",  
                  "properties": {  
                    "name": {  
                      "type": "string"  
                    },  
                    "filterExpression": {  
                      "anyOf": [  
                        {  
                          "type": "string"  
                        },  
                        {  
                          "type": "array",  
                          "items": {  
                            "type": "string"  
                          }  
                        }  
                      ]  
                    },  
                    "annotations": {  
                      "type": "array",  
                      "items": {  
                        "description": "Annotation object of Tabular Object Model (TOM)",  
                        "type": "object",  
                        "properties": {  
                          "name": {  
                            "type": "string"  
                          },  
                          "value": {  
                            "anyOf": [  
                              {  
                                "type": "string"  
                              },  
                              {  
                                "type": "array",  
                                "items": {  
                                  "type": "string"  
                                }  
                              }  
                            ]  
                          }  
                        },  
                        "additionalProperties": false  
                      }  
                    }  
                  },  
                  "additionalProperties": false  
                }  
              }  
            },  
            "additionalProperties": false  
          }  
        }  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Tabular Model Scripting Language &#40;TMSL&#41; – Referenz](../../analysis-services/tabular-model-scripting-language-tmsl-reference.md)   
 [Rollen und Berechtigungen &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/roles-and-permissions-analysis-services.md)  
  
  