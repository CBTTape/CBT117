# CBT117
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. 
Due to amazing work by Alison Zhang and Jake Choi repos are no longer deleted.

```
//***FILE 117 IS A SERIES OF WTO EXITS FROM JAMES COOK OF COCA      *   FILE 117
//*           COLA IN ATLANTA GEORGIA                               *   FILE 117
//*                                                                 *   FILE 117
//*           USING THE "MESSAGE PROCESSING FACILITY"               *   FILE 117
//*             OTHERWISE KNOWN AS "MANY WTO EXITS"                 *   FILE 117
//*                                                                 *   FILE 117
//*      ENCLOSED ARE SEVERAL WTO EXITS WRITTEN ACCORDING TO        *   FILE 117
//*      THE STANDARDS OF THE "MESSAGE PROCESSING FACILITY"         *   FILE 117
//*      UNDER MVS/SP2.1.2.  THESE EXITS HAVE REPLACED "R2D2"       *   FILE 117
//*      FROM THE CBT TAPE.  OTHER FEATURES OF "R2D2" ARE NOT       *   FILE 117
//*      USED AT OUR CENTER.  NO CHANGE WAS MADE TO RUN UNDER       *   FILE 117
//*      MVS/SP2.1.3.                                               *   FILE 117
//*                                                                 *   FILE 117
//*      THE EXITS MUST BE ASSEMBLED AS "RENT,NOALIGN" AND          *   FILE 117
//*      LINK-EDITED WITH THE OPTIONS "RENT,REUS" INTO THE LINK     *   FILE 117
//*      LIST.  THE "MPFLSTXX" MUST BE IN SYS1.PARMLIB AND AN       *   FILE 117
//*      ENTRY MADE IN "IEASYSXX".                                  *   FILE 117
//*                                                                 *   FILE 117
//*      THESE EXITS CAN ABEND ANYWHERE AND NOT CAUSE ANY           *   FILE 117
//*      PROBLEMS.  THE ONLY PROBLEM THAT I HAVE NOTICED IN         *   FILE 117
//*      IMPLEMENTING ANY MPF EXIT IS THAT THE IEZMGCR MACRO        *   FILE 117
//*      FROM IBM MUST HAVE AN "ORG" IMMEDIATELY AFTER IT TO        *   FILE 117
//*      PREVENT PROBLEMS.                                          *   FILE 117
//*                                                                 *   FILE 117
//*      IF "IEAVMXIT" IS LINKED INTO THE LINKLIST, IT WILL BE      *   FILE 117
//*      USED.  IT NEEDS NO ENTRY IN "MPFLSTXX".                    *   FILE 117
//*                                                                 *   FILE 117
//*      MOST OF THE EXITS ARE SELF-EXPLANATORY.  THE ONES THAT     *   FILE 117
//*      ARE IMPLEMENTED NOW ARE:                                   *   FILE 117
//*                                                                 *   FILE 117
//*        01 WTODB103  WTO EXIT- DATACOM/DB BACKOUT MESSAGE        *   FILE 117
//*        02 WTOD1001  WTO EXIT TO SCHEDULE DATACOM PXX CLEAR TASK *   FILE 117
//*        03 WTOECVT   MACRO TO STORE FIELDS FROM IMS /DIS A       *   FILE 117
//*        04 WTOEDB30  WTO EXIT TO DUMP DATACOM-DB LOG             *   FILE 117
//*        05 WTOEF97I  WTO EXIT TO SUPPRESS MSG IEF097I            *   FILE 117
//*        06 WTOEIUTL  WTO EXIT TO ISSUE IMS /DIS A                *   FILE 117
//*        07 WTOEI000  WTO EXIT TO INTERPRET IMS /DIS A            *   FILE 117
//*        08 WTOEI554  WTO EXIT TO INTERPRET IMS /DIS A            *   FILE 117
//*        09 WTOEI996  WTO EXIT TO SAVE IMS REPLY NUMBER           *   FILE 117
//*        10 WTOENROL  WTO EXIT TO STOP A MESSAGE FROM ROLLING     *   FILE 117
//*        11 WTOERD    WTOR EXIT TO REPLY "D" TO MESSAGE           *   FILE 117
//*        12 WTOERHLD  WTOR EXIT TO REPLY "HOLD" TO MSG IEF225D    *   FILE 117
//*        13 WTOERM    WTOR EXIT TO REPLY "M" TO MESSAGE           *   FILE 117
//*        14 WTOERNHL  WTOR EXIT TO REPLY "NOHOLD" TO MESSAGE      *   FILE 117
//*        15 WTOEROLL  WTO EXIT TO CAUSE A MESSAGE TO ROLL         *   FILE 117
//*        16 WTOERU    WTOR EXIT TO REPLY "U" TO MESSAGE           *   FILE 117
//*        17 WTOERWAT  WTOR EXIT TO REPLY "WAIT" TO MESSAGE        *   FILE 117
//*        18 WTOERY    WTOR EXIT TO REPLY "Y"                      *   FILE 117
//*        19 WTOER301  WTOR EXIT TO REPLY "JOBNAME" TO IEC301A     *   FILE 117
//*        20 WTOETPS1  WTO EXIT TO CAPTURE TAPE UNLOAD DATA        *   FILE 117
//*        21 WTOETPS2  WTO EXIT TO DISPLAY TAPE UNLOADED DATA      *   FILE 117
//*        22 WTOE176I  WTO EXIT TO STOP EXTERNAL WRITER            *   FILE 117
//*        23 WTOE315I  PROCESS NPM MSGFNM315I AT SHUTDOWN          *   FILE 117
//*        24 WTOE362A  WTO EXIT TO DUMP AN SMF MANX DATASET        *   FILE 117
//*                                                                 *   FILE 117
//*      THE TWO EXITS "WTOETPSN" ARE USED TO STORE THE LAST        *   FILE 117
//*      TAPE USED ON EACH TAPE DRIVE AND DISPLAY IT FOR THE        *   FILE 117
//*      OPERATOR WHEN ANOTHER MOUNT FOR THAT TAPE IS ISSUED.       *   FILE 117
//*      THE MESSAGE IS "TAPE XXXXXX MAY STILL BE ON DRIVE          *   FILE 117
//*      XXX".  THIS WAS DESIGNED FOR THE IBM 3480 TAPE DRIVE       *   FILE 117
//*      WITH THE TAPE STACKER FEATURE BECAUSE IT CAN HOLD SIX      *   FILE 117
//*      "USED" TAPES PER DRIVE.  IN OUR SHOP, THAT WORKS OUT       *   FILE 117
//*      TO A MAXIMUM OF 148 TAPES THAT ARE STILL ON THE TAPE       *   FILE 117
//*      DRIVES (UP FROM 28 BEFORE THE TAPE STACKER FEATURE)        *   FILE 117
//*      AND EFFECTIVELY LOST AS FAR AS THE TAPE OPERATORS ARE      *   FILE 117
//*      CONCERNED.  THE TAPE CONFIGURATION MUST BE ASSEMBLED       *   FILE 117
//*      INTO THE WTOETPS1 EXIT WITH THE INTERNALLY DEFINED         *   FILE 117
//*      "STRING" MACRO.  THE TABLE TO HOLD THE TAPE VOLUME         *   FILE 117
//*      SERIAL NUMBER AND THE TAPE DRIVE ADDRESS IS IN             *   FILE 117
//*      EXTENDED CSA. THE TABLE IS POINTED TO BY A FIELD IN        *   FILE 117
//*      OUR USERCVT (NOT SUPPLIED) THAT IS ANCHORED IN THE         *   FILE 117
//*      CVTUSER FIELD OF THE MVS CVT.  THE EXITS DO A LOT OF       *   FILE 117
//*      VALIDITY CHECKING SO EITHER EXIT CAN BE INSTALLED          *   FILE 117
//*      FIRST.                                                     *   FILE 117
//*                                                                 *   FILE 117
//*      THE "WTOEIXXX" EXITS ARE TO AUTOMATICALLY CANCEL IMS       *   FILE 117
//*      BMPS THROUGH THE OUTSTANDING REPLY.  THEY DEPEND           *   FILE 117
//*      HEAVILY ON OUR USERCVT AND WILL NOT ASSEMBLE WITHOUT       *   FILE 117
//*      IT OR A REPLACEMENT.  THEY ARE INCLUDED AS AN EXAMPLE      *   FILE 117
//*      OF WHAT CAN BE DONE USING WTO EXITS TO PROCESS             *   FILE 117
//*      MULTIPLE, ASYNCHRONOUS MESSAGES.                           *   FILE 117
//*                                                                 *   FILE 117
//*      SUPPORTED BY:                                              *   FILE 117
//*           JAMES F. COOK                                         *   FILE 117
//*           THE COCA-COLA COMPANY                                 *   FILE 117
//*           ONE COCA-COLA PLAZA, N.W.                             *   FILE 117
//*           ATLANTA, GA  30313                                    *   FILE 117
//*           (404) 676-8522                                        *   FILE 117
//*                                                                 *   FILE 117
//*      email:  jacook@na.ko.com                                   *   FILE 117
//*                                                                 *   FILE 117
```
