# Luna
library(foreign)
library(ENmisc)
####combine demographic data,grage,cotinine and cadmium data from 1999-2012
####### data 1999-2000
demoa<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DEMO.XPT")  ####9965 obs, 144 variables
blooda<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/LAB06.XPT") ####8832 obs, 41 variables
garagea<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/LAB21.XPT")  ######851 obs of 53 variables, garage 650
diabetesa<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DIQ.XPT") #####9493 obs of 17 variables
smokinga<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/SMQ.XPT") ####4880 obs of 39 variables
reproa<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/RHQ.XPT") #### 3517 obs of 90 vairables
######
str(demoa)
str(blooda)
data_a1<-merge(demoa,blooda,by="SEQN")
data_a<-merge(demoa,blooda, by="SEQN",all.x=TRUE) #######9965 obs, 184 variables
data_a<-merge(data_a,diabetesa,by="SEQN",all.x=TRUE) ###### 200 variables
data_a<-merge(data_a,smokinga,by="SEQN",all.x=TRUE)  ### 238 variables
data_a<-merge(data_a,garagea, by="SEQN",all.x=TRUE) #####9965 obs of 290 variables
data_a<-merge(data_a,reproa, by = "SEQN",all.x=TRUE) ####### 9965 obs of 379 variables
str(data_a)
demob<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DEMO_B.XPT") #####11039 obs, 37 variables
bloodb<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/L06_B.XPT")  #####9929 obs, 22 variables
diabetesb<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DIQ_B.XPT") #####9493 obs of 17 variables
smokingb<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/SMQ_B.XPT") ####4880 obs of 39 variables
reprob<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/RHQ_B.XPT")
str(demob)
str(bloodb)
data_b<-merge(demob,bloodb, by="SEQN",all.x=TRUE) ###### 11039 samples, 58 varaibles
data_b<-merge(data_b,diabetesb,by="SEQN",all.x=TRUE) 
data_b<-merge(data_b,smokingb,by="SEQN",all.x=TRUE)
data_b<-merge(data_b,reprob,by="SEQN",all.x=TRUE) ###11039 obs of 218 variables
str(data_b)
democ<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DEMO_C.XPT") ### 10122 obs, 44 variables
bloodc<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/L06BMT_C.XPT") ### 9179 obs, 9 variables
cotininec<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/L06COT_C.XPT") ####8556 obs of 2 varaibles
garagec<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/L04VOC_C.XPT") ###1489 obs of 98 variables
foodc<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/FFQRAW_C.XPT")  ####6472 obs of 225 variables
diabetesc<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DIQ_C.XPT") 
smokingc<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/SMQ_C.XPT") 
reproc<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/RHQ_C.XPT")
str(democ)
str(bloodc)
data_c<-merge(democ,bloodc, by="SEQN",all.x=TRUE) #### 10122 obs, 52 variables
data_c<-merge(data_c,cotininec, by="SEQN",all.x=TRUE) #####10122 of of 53 variables
data_c<-merge(data_c,garagec,by="SEQN",all.x=TRUE)  ######10122 obs of 150
data_c<-merge(data_c,foodc,by="SEQN",all.x=TRUE) ######10122 obs of 374
data_c<-merge(data_c,diabetesc,by="SEQN",all.x=TRUE)  #####10122 obs of 390
data_c<-merge(data_c,smokingc,by="SEQN",all.x=TRUE)  ####10122 obs of 431 
data_c<-merge(data_c,reproc,by="SEQN",all.x=TRUE)  ####10122 ofs of 522 
data_c1<-merge(data_c,garagec, by="SEQN",all.x=TRUE)  #### 1489 obs of 150 variabels
write.csv(data_c1,file="data_c1.csv")
data_c1<-read.csv("/Users/Luna/Documents/Capstone/NHANES data/data_c1.csv")
str(data_c1)
str(garagec)
str(data_c)
demod<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DEMO_D.XPT") ###10348 obs, 43 variables
bloodd<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/PBCD_D.XPT") ### 9440 obs, 8 variables
cotinined<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/COT_D.XPT") ######8753 obs of 2 variables
garaged<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/VOC_D.XPT") ####3545 obs of 33 variabels
foodd<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/FFQRAW_D.XPT") #### 6013 obs of 225 variabels
diabetesd<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DIQ_D.XPT") 
smokingd<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/SMQ_D.XPT") 
reprod<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/RHQ_D.XPT")
str(demod)
str(bloodd)
data_d <- merge(demod, bloodd, by="SEQN",all.x=TRUE)  ####### 10348 obs, 50 variables
data_d<-merge(data_d,cotinined, by ="SEQN",all.x=TRUE) ##### 10348 obs 51 variable
data_d<-merge(data_d,garaged,by="SEQN",all.x=TRUE)  ###   83
data_d<-merge(data_d,foodd,by="SEQN",all.x=TRUE)  #####  307
data_d<-merge(data_d,diabetesd,by="SEQN",all.x=TRUE) ##### 342
data_d<-merge(data_d,smokingd,by="SEQN",all.x=TRUE) ###### 380
data_d<-merge(data_d,reprod,by="SEQN",all.x=TRUE)   #######  464
data_d1<- merge(data_d, garaged, by="SEQN",all.x=TRUE) ######3545 obs 83 obs
write.csv(data_d1, file=("data_d1.csv"))
data_d1<-read.csv("/Users/Luna/Documents/Capstone/NHANES data/data_d1.csv") ###10348 obs of 464 variables
str(data_d1)
str(data_d)
demoe<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DEMO_E.XPT") #####10149 obs, 43 variabels
bloode<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/PBCD_E.XPT")  ###### 9307 obs, 8 variables
cotininee<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/COTNAL_E.XPT") #### 8712 obs of 6 variabels
garagee<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/VOC_E.XPT")  #######3415 obs of 33 variables
diabetese<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DIQ_E.XPT") 
smokinge<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/SMQ_E.XPT") 
reproe<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/RHQ_E.XPT")
str(demoe)
str(bloode)
data_e<- merge(demoe, bloode, by="SEQN",all.x=TRUE)  ##### 10149 obs, 50 variabels
data_e<- merge(data_e, cotininee, by= "SEQN",all.x=TRUE) ####10149 obs 55 variables
data_e<-merge(data_e,garagee,by="SEQN",all.x=TRUE)  #####  10149 obs of 87
data_e<-merge(data_e,diabetese,by="SEQN",all.x=TRUE)  ##### 10149 obs of 122
data_e<-merge(data_e,smokinge,by="SEQN",all.x=TRUE)   ###  10149 obs of 158
data_e<-merge(data_e,reproe,by="SEQN",all.x=TRUE)   ###### 10149 obs of 215
data_e1<-merge(data_e, garagee, by="SEQN",all.x=TRUE) ####8712 obs 87 variabels
write.csv(data_e1,file=("data_e1.csv"))
data_e1<-read.csv("/Users/Luna/Documents/Capstone/NHANES data/data_e1.csv") ######10149 obs of 248 variables
str(data_e) 
demof<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DEMO_F.XPT") #####10537 obs, 43 variables
bloodf<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/PBCD_F.XPT") ##### 9835 obs, 10 variabels
cotininef<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/COTNAL_F.XPT")  ###### 9211 obs of 6 variables
diabetesf<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DIQ_F.XPT") 
smokingf<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/SMQ_F.XPT") 
reprof<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/RHQ_F.XPT")
str(demof)
str(bloodf)
data_f<-merge(demof,bloodf, by="SEQN",all.x=TRUE)  #####  10537 obs, 52 variabels
data_f<-merge(data_f, cotininef, by="SEQN",all.x=TRUE) #####  10537 obs of 57 variables
data_f<-merge(data_f,diabetesf, by = "SEQN", all.x = TRUE)   #####76
data_f<-merge(data_f, smokingf, by = "SEQN", all.x = TRUE)  
data_f<-merge(data_f, reprof, by = "SEQN", all.x = TRUE)   ##### 10537 obs of 169 variable
str(data_f)
demog<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DEMO_G.XPT") #####9756 obs, 48 variables
bloodg<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/PBCD_G.XPT")  ##### 8956 obs, 16 variables
cotinineg<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/COTNAL_G.XPT") ###### 8435 obs of 6 variabels
diabetesg<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/DIQ_G.XPT") 
smokingg<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/SMQ_G.XPT") 
reprog<-read.xport("/Users/Luna/Documents/Capstone/NHANES data/RHQ_G.XPT")
str(demog)
str(bloodg)
data_g<-merge(demog, bloodg, by="SEQN", all.x = TRUE)  ###### 8956 obs, 63 variables
data_g<-merge(data_g, cotinineg,by="SEQN", all.x = TRUE) ######8435 obs of 68 variables
data_g<-merge(data_g, diabetesg, by = "SEQN", all.x = TRUE)
data_g<-merge(data_g, smokingg, by = "SEQN", all.x = TRUE)
data_g<-merge(data_g, reprog, by = "SEQN", all.x = TRUE)   #######9756 obs of 206 variables
str(demog)

####### total blood cadmium among all population  #########
totala<- subset(data_a, select = c("SEQN","SDDSRVYR","RIDEXMON","RIAGENDR","RIDAGEYR","RIDRETH1",
                                   "DMDCITZN","INDFMPIR","LBXBCD",
                                   "LBDBCDSI","LBXCOT","WTINT2YR","WTMEC2YR","SDMVPSU","SDMVSTRA",
                                   "DIQ010", "SMQ020","SMQ040","RHQ140"))
colnames(totala)[19]<-"RHD143"
str(data_a)
str(totala)  ######19 variables
totalb<- subset(data_b, select = c("SEQN","SDDSRVYR","RIDEXMON", "RIAGENDR","RIDAGEYR","RIDRETH1",
                                   "DMDCITZN","INDFMPIR","LBXBCD",
                                   "LBDBCDSI","LBXCOT","WTINT2YR","WTMEC2YR","SDMVPSU","SDMVSTRA",
                                   "DIQ010","SMQ020","SMQ040","RHQ141"))
colnames(totalb)[19]<-"RHD143"
totalc<- subset(data_c, select = c("SEQN","SDDSRVYR","RIDEXMON","RIAGENDR","RIDAGEYR","RIDRETH1",
                                   "DMDCITZN","INDFMPIR","LBXBCD",
                                   "LBDBCDSI","LBXCOT","WTINT2YR","WTMEC2YR","SDMVPSU","SDMVSTRA",
                                   "DIQ010","SMQ020","SMQ040","RHD143"))
totald<- subset(data_d, select = c("SEQN","SDDSRVYR","RIDEXMON","RIAGENDR","RIDAGEYR","RIDRETH1",
                                   "DMDCITZN","INDFMPIR","LBXBCD",
                                   "LBDBCDSI","LBXCOT","WTINT2YR","WTMEC2YR","SDMVPSU","SDMVSTRA",
                                   "DIQ010","SMQ020","SMQ040","RHD143"))
totale<- subset(data_e, select = c("SEQN","SDDSRVYR","RIDEXMON","RIAGENDR","RIDAGEYR","RIDRETH1",
                                   "DMDCITZN","INDFMPIR","LBXBCD",
                                   "LBDBCDSI","LBXCOT","WTINT2YR","WTMEC2YR","SDMVPSU","SDMVSTRA",
                                   "DIQ010","SMQ020","SMQ040","RHD143"))
totalf<- subset(data_f, select = c("SEQN","SDDSRVYR","RIDEXMON","RIAGENDR","RIDAGEYR","RIDRETH1",
                                   "DMDCITZN","INDFMPIR","LBXBCD",
                                   "LBDBCDSI","LBXCOT","WTINT2YR","WTMEC2YR","SDMVPSU","SDMVSTRA",
                                   "DIQ010","SMQ020","SMQ040","RHD143"))
totalg<- subset(data_g, select = c("SEQN","SDDSRVYR","RIDEXMON","RIAGENDR","RIDAGEYR","RIDRETH1",
                                   "DMDCITZN","INDFMPIR","LBXBCD",
                                   "LBDBCDSI","LBXCOT","WTINT2YR","WTMEC2YR","SDMVPSU","SDMVSTRA",
                                   "DIQ010","SMQ020","SMQ040","RHD143"))
alldata<-rbind(totala,totalb,totalc,totald,totale,totalf,totalg) ###71916 obs of 19 variables
alldatatrend<-alldata[complete.cases(alldata[,1:15]),]  #######50296 obs of 19 variables
alldatatrend["MEC4YR"]<-NA
alldatatrend["INT4YR"]<-NA
alldatatrend$MEC4YR<-ifelse (alldatatrend$SDDSRVYR==1|alldatatrend$SDDSRVYR==2,alldatatrend$WTMEC2YR/2,NA) 
alldatatrend$INT4YR<-ifelse (alldatatrend$SDDSRVYR==1|alldatatrend$SDDSRVYR==2,alldatatrend$WTINT2YR/2,NA)
alldatatrend["MEC14YR"]<-NA
alldatatrend["INT14YR"]<-NA
alldatatrend$MEC14YR <- ifelse (alldatatrend$SDDSRVYR==1|alldatatrend$SDDSRVYR==2,(2/7)*alldatatrend$MEC4YR,alldatatrend$WTMEC2YR/7)
alldatatrend$INT14YR <- ifelse (alldatatrend$SDDSRVYR==1|alldatatrend$SDDSRVYR==2,(2/7)*alldatatrend$INT4YR,alldatatrend$WTINT2YR/7)
alldatatrend["year"]<-NA
alldatatrend['MEC12YR']<-NA
alldatatrend['INT12YR']<-NA
alldatatrend$MEC12YR<- ifelse (alldatatrend$SDDSRVYR==2,(2/6)*alldatatrend$MEC4YR,alldatatrend$WTMEC2YR/6)
alldatatrend$INT12YR<- ifelse (alldatatrend$SDDSRVYR==2,(2/6)*alldatatrend$MEC4YR,alldatatrend$WTMEC2YR/6)
alldatatrend$year[alldatatrend$SDDSRVYR==1]<-'1999-2000'
alldatatrend$year[alldatatrend$SDDSRVYR==2]<-'2001-2002'
alldatatrend$year[alldatatrend$SDDSRVYR==3]<-'2003-2004'
alldatatrend$year[alldatatrend$SDDSRVYR==4]<-'2005-2006'
alldatatrend$year[alldatatrend$SDDSRVYR==5]<-'2007-2008'
alldatatrend$year[alldatatrend$SDDSRVYR==6]<-'2009-2010'
alldatatrend$year[alldatatrend$SDDSRVYR==7]<-'2011-2012'
library(weights)
write.csv(alldatatrend,file="alldatatrend.csv")
alldatatrend<-read.csv(file="/Users/Luna/Documents/Capstone/NHANES data/alldatatrend.csv")
alldatatrend["race"]<-NA
alldatatrend$race<-ifelse(alldatatrend$RIDRETH1==1,'Mexican American',alldatatrend$race)
alldatatrend$race<-ifelse(alldatatrend$RIDRETH1==4,'Non-Hispanic Black',alldatatrend$race)
alldatatrend$race<-ifelse(alldatatrend$RIDRETH1==3,'Non-Hispanic White',alldatatrend$race)
alldatatrend$race<-ifelse(alldatatrend$RIDRETH1==2|alldatatrend$RIDRETH1==5,'Other',alldatatrend$race)
alldatatrend["gender"]<-NA
alldatatrend$gender<-ifelse(alldatatrend$RIAGENDR==1,'male','female')
alldatatrend["pregnant"]<-1
alldatatrend["diabetes"]<-0
alldatatrend$diabetes<-ifelse(alldatatrend$DIQ010==1,1,0)
alldatatrend$diabetes[is.na(alldatatrend$diabetes)]<-0
alldatatrend$pregnant<-ifelse(alldatatrend$RHD143==1,1,0)
alldatatrend$pregnant[is.na(alldatatrend$pregnant)]<-0
alldatatrend<-subset(alldatatrend[alldatatrend$pregnant==0,]) ##### delete 1067 female who think they are pregnant, 49229 obs
alldatatrend["smoking"]<-NA
alldatatrend$smoking<-ifelse(alldatatrend$SMQ020==1&alldatatrend$SMQ040==3,"Former smoker",alldatatrend$smoking)
alldatatrend$smoking<-ifelse(alldatatrend$SMQ020==1&alldatatrend$SMQ040!=3,"Current smoker",alldatatrend$smoking)
alldatatrend$smoking<-ifelse(12<alldatatrend$RIDAGEYR&alldatatrend$RIDAGEYR<20&alldatatrend$LBXCOT>1.18&alldatatrend$race=='Mexican American',
                             "Current smoker",alldatatrend$smoking)
alldatatrend$smoking<-ifelse(12<alldatatrend$RIDAGEYR&alldatatrend$RIDAGEYR<20&alldatatrend$LBXCOT>2.77&alldatatrend$race=='Non-Hispanic Black',
                             "Current smoker",alldatatrend$smoking)
alldatatrend$smoking<-ifelse(12<alldatatrend$RIDAGEYR&alldatatrend$RIDAGEYR<20&alldatatrend$LBXCOT>2.95&alldatatrend$race=='Non-Hispanic White',
                             "Current smoker",alldatatrend$smoking)
alldatatrend$smoking<-ifelse(12<alldatatrend$RIDAGEYR&alldatatrend$RIDAGEYR<20&alldatatrend$LBXCOT>2.99&alldatatrend$race=='Other',
                             "Current smoker",alldatatrend$smoking)
alldatatrend$smoking[is.na(alldatatrend$smoking)]<-"Non-smoker"
alldatatrend["agelevel"]<-NA
alldatatrend$agelevel<-ifelse(alldatatrend$RIDAGEYR<12,'<12',alldatatrend$agelevel)
alldatatrend$agelevel<-ifelse(alldatatrend$RIDAGEYR>11&alldatatrend$RIDAGEYR<21,'12~20',alldatatrend$agelevel)
alldatatrend$agelevel<-ifelse(alldatatrend$RIDAGEYR>20&alldatatrend$RIDAGEYR<46,'21~45',alldatatrend$agelevel)
alldatatrend$agelevel<-ifelse(alldatatrend$RIDAGEYR>45&alldatatrend$RIDAGEYR<66,'46~65',alldatatrend$agelevel)
alldatatrend$agelevel<-ifelse(alldatatrend$RIDAGEYR>65,'65+',alldatatrend$agelevel)

#############
############# save data file
##############
write.csv(alldatatrend,file="alldatatrend.csv")
alldatatrend<-read.csv(file="/Users/Luna/Documents/Capstone/NHANES data/alldatatrend.csv")

wtd.mean(alldatatrend$LBXBCD,weights=alldatatrend$MEC14YR,normwt="ignored",na.rm=TRUE)
wtd.var(alldatatrend$LBXBCD,weights=alldatatrend$MEC14YR, normwt=FALSE, na.rm=TRUE)
library(survey) ########## weighted proportion
data1999<-alldatatrend[alldatatrend$SDDSRVYR==1,]
data2001<-alldatatrend[alldatatrend$SDDSRVYR==2,]
data2003<-alldatatrend[alldatatrend$SDDSRVYR==3,]
data2005<-alldatatrend[alldatatrend$SDDSRVYR==4,]
data2007<-alldatatrend[alldatatrend$SDDSRVYR==5,]
data2009<-alldatatrend[alldatatrend$SDDSRVYR==6,]
data2011<-alldatatrend[alldatatrend$SDDSRVYR==7,]
######### descriptive of data
table(alldatatrend$year)
wtd.mean(data1999$LBXBCD,weights=data1999$MEC14YR,normwt="ignored",na.rm=TRUE)

wtd.quantile(alldatatrend$RIDAGEYR,weights=alldatatrend$MEC14YR)
wtd.quantile(data1999$RIDAGEYR,weights=data1999$MEC14YR)
wtd.quantile(data2001$RIDAGEYR,weights=data2001$MEC14YR)
wtd.quantile(data2003$RIDAGEYR,weights=data2003$MEC14YR)
wtd.quantile(data2005$RIDAGEYR,weights=data2005$MEC14YR)
wtd.quantile(data2007$RIDAGEYR,weights=data2007$MEC14YR)
wtd.quantile(data2009$RIDAGEYR,weights=data2009$MEC14YR)
wtd.quantile(data2011$RIDAGEYR,weights=data2011$MEC14YR)

alldatatrend1<-alldatatrend[alldatatrend$detect==1,]
wtd.quantile(alldatatrend1$RIDAGEYR,weights=alldatatrend1$MEC14YR)
wtd.quantile(data1999$RIDAGEYR,weights=data1999$MEC14YR)
wtd.quantile(data2001$RIDAGEYR,weights=data2001$MEC14YR)
wtd.quantile(data2003$RIDAGEYR,weights=data2003$MEC14YR)
wtd.quantile(data2005$RIDAGEYR,weights=data2005$MEC14YR)
wtd.quantile(data2007$RIDAGEYR,weights=data2007$MEC14YR)
wtd.quantile(data2009$RIDAGEYR,weights=data2009$MEC14YR)
wtd.quantile(data2011$RIDAGEYR,weights=data2011$MEC14YR)

############## under detection  ################
data1999['detect']<-NA
data1999['detect3']<-NA
data1999$detect<-ifelse(data1999$LBXBCD<0.3,0,1)
data1999$detect3<-ifelse(data1999$LBXBCD<0.3,0,1)
table(data1999$detect, data1999$smoking)
data2001['detect']<-NA
data2001['detect3']<-NA
data2001$detect<-ifelse(data2001$LBXBCD<0.3,0,1)
data2001$detect3<-ifelse(data2001$LBXBCD<0.3,0,1)
table(data2001$detect, data2001$smoking)
data2001<-subset(data2001,select=-undetect)
data2003['detect']<-NA
data2003['detect3']<-NA
data2003$detect<-ifelse(data2003$LBXBCD<0.2,0,1)
data2003$detect3<-ifelse(data2003$LBXBCD<0.3,0,1)
table(data2003$detect, data2003$smoking)
table(data2003$detect3,data2003$smoking)
data2005['detect']<-NA
data2005['detect3']<-NA
data2005$detect<-ifelse(data2005$LBXBCD<0.2,0,1)
data2005$detect3<-ifelse(data2005$LBXBCD<0.3,0,1)
table(data2005$detect, data2005$smoking)
table(data2005$detect3, data2005$smoking)

data2007['detect']<-NA
data2007['detect3']<-NA
data2007$detect<-ifelse(data2007$LBXBCD<0.2,0,1)
data2007$detect3<-ifelse(data2007$LBXBCD<0.3,0,1)
table(data2007$detect, data2007$smoking)
table(data2007$detect3, data2007$smoking)

data2009['detect']<-NA
data2009['detect3']<-NA
data2009$detect<-ifelse(data2009$LBXBCD<0.2,0,1)
data2009$detect3<-ifelse(data2009$LBXBCD<0.3,0,1)
table(data2009$detect, data2009$smoking)
table(data2009$detect3, data2009$smoking)

data2011['detect']<-NA
data2001['detect3']<-NA
data2011$detect<-ifelse(data2011$LBXBCD<0.2,0,1)
data2011$detect3<-ifelse(data2011$LBXBCD<0.3,0,1)
table(data2011$detect, data2011$smoking)
table(data2011$detect3, data2011$smoking)

alldatatrend<-rbind(data1999,data2001,data2003,data2005,data2007,data2009,data2011)
alldatatrend['detect3']<-NA
alldatatrend['']
alldatatrend$detect3<-ifelse(alldatatrend$LBXBCD<0.3,0,1)
table(alldatatrend$detect,alldatatrend$detect3)
detect<-alldatatrend[alldatatrend$detect==1,]
undetect<-alldatatrend[alldatatrend$detect==0,]
alldatatrend<-read.csv(file="/Users/Luna/Documents/Capstone/NHANES data/alldatatrend.csv")
library(ggplot2)
alldatatrend1<-alldatatrend[alldatatrend$detect==1,]
str(alldatatrend1[alldatatrend1$smoking=='Current smoker',])
str(alldatatrend1[alldatatrend1$smoking=='Former smoker',])
str(alldatatrend[alldatatrend$smoking=='Former smoker',])
str(alldatatrend1[alldatatrend1$smoking=='Non-smoker',])
str(alldatatrend[alldatatrend$smoking=='Non-smoker',])
glmall<-lm(log(LBXBCD)~SDDSRVYR+gender+smoking+race+RIDAGEYR,weight=MEC14YR,data=alldatatrend1)
summary(glmall)
smoker<-alldatatrend[alldatatrend$smoking=='Current smoker',]
glmall<-lm(log(LBXBCD)~SDDSRVYR+gender+smoking+race+RIDAGEYR,weight=MEC14YR,data=alldatatrend1)
data19991<-data1999[data1999$detect==1,]
data19991<-data19991[data19991$smoking=='Current smoker',]
ggplot(data19991,aes(x=log(LBXBCD)))+
        geom_histogram(binwidth=0.25)
shapiro.test(log(data19991$LBXBCD))
qqnorm(log(data19991$LBXBCD))
qqline(log(data19991$LBXBCD))
bar=mean(log(alldatatrend$LBXBCD))
s=sd(log(alldatatrend$LBXBCD))
curve(dnorm(log(alldatatrend$LBXBCD),bar,s),col=2,add=TRUE)
plot(density(log(alldatatrend$LBXBCD)))
shapiro.test(log(alldatatrend$LBXBCD))
########### calculate the rate of under detect limitation
data1999sm<-data1999[data1999$smoking=='Current smoker',]
table(data1999sm$detect)
data1999fsm<-data1999[data1999$smoking=='Former smoker',]
table(data1999fsm$detect)
data1999nsm<-data1999[data1999$smoking=='Non-smoker',]
table(data1999nsm$detect)

data2001sm<-data2001[data2001$smoking=='Current smoker',]
table(data2001sm$detect)
data2001fsm<-data2001[data2001$smoking=='Former smoker',]
table(data2001fsm$detect)
data2001nsm<-data2001[data2001$smoking=='Non-smoker',]
table(data2001nsm$detect)

data2003sm<-data2003[data2003$smoking=='Current smoker',]
table(data2003sm$detect)
data2003fsm<-data2003[data2003$smoking=='Former smoker',]
table(data2003fsm$detect)
data2003nsm<-data2003[data2003$smoking=='Non-smoker',]
table(data2003nsm$detect)

data2005sm<-data2005[data2005$smoking=='Current smoker',]
table(data2005sm$detect)
data2005fsm<-data2005[data2005$smoking=='Former smoker',]
table(data2005fsm$detect)
data2005nsm<-data2005[data2005$smoking=='Non-smoker',]
table(data2005nsm$detect)

data2005sm<-data2005[data2005$smoking=='Current smoker',]
table(data2005sm$detect)
data2005fsm<-data2005[data2005$smoking=='Former smoker',]
table(data2005fsm$detect)
data2005nsm<-data2005[data2005$smoking=='Non-smoker',]
table(data2005nsm$detect)

data2007sm<-data2007[data2007$smoking=='Current smoker',]
table(data2007sm$detect)
data2007fsm<-data2007[data2007$smoking=='Former smoker',]
table(data2007fsm$detect)
data2007nsm<-data2007[data2007$smoking=='Non-smoker',]
table(data2007nsm$detect)

data2009sm<-data2009[data2009$smoking=='Current smoker',]
table(data2009sm$detect)
data2009fsm<-data2009[data2009$smoking=='Former smoker',]
table(data2009fsm$detect)
data2009nsm<-data2009[data2009$smoking=='Non-smoker',]
table(data2009nsm$detect)

data2011sm<-data2011[data2011$smoking=='Current smoker',]
table(data2011sm$detect)
data2011fsm<-data2011[data2011$smoking=='Former smoker',]
table(data2011fsm$detect)
data2011nsm<-data2011[data2011$smoking=='Non-smoker',]
table(data2011nsm$detect)

library(NADA)
plot(cenfit(alldatatrend$LBXBCD,alldatatrend$detect))
alldatatrend$cencd<-NA
alldatatrend$cencd<-ifelse(alldatatrend$detect==1,TRUE, FALSE)
alldatatrend$logcadmium<-NA
alldatatrend$logcadmium<-log(alldatatrend$LBXBCD)
cdcam<-cenfit(alldatatrend$LBXBCD,alldatatrend$cencd)
cdcam
plot(cdcam)

detect<-alldatatrend[alldatatrend$detect3==1,]
detect1999<-detect[detect$SDDSRVYR==1,]
wtd.mean(detect1999$RIDAGEYR,weights=detect1999$MEC14YR,normwt="ignored",na.rm=TRUE)
d1999<-svydesign(ids=detect1999$SEQN, data=detect1999,weights=detect1999$MEC14YR)
prop.table(svytable(~detect1999$race, design=d1999))
prop.table(svytable(~detect1999$smoking, design=d1999))
prop.table(svytable(~detect1999$gender, design=d1999))
prop.table(svytable(~detect1999$diabetes, design=d1999))
prop.table(svytable(~detect1999$agelevel, design=d1999))
