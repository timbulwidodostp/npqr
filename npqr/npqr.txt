# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Nonparametric series quantile regression Use npqr (quantreg.nonpar) With (In) R Software
install.packages("quantreg.nonpar")
library("quantreg.nonpar")
npqr = read.csv("https://raw.githubusercontent.com/timbulwidodostp/npqr/main/npqr/npqr.csv",sep = ";")
# Estimation Nonparametric series quantile regression Use npqr (quantreg.nonpar) With (In) R Software
formula=cheight~mbmi+breastfeeding+mage+medu+edupartner
basis.bsp <- create.bspline.basis(breaks=quantile(npqr$cage,c(0:10)/10))
n=length(npqr$cage)
B=500
alpha=.95
taus=c(1:24)/25
print.taus=c(1:4)/5
piv.bsp <- npqr(formula=formula, data=npqr, basis=basis.bsp, var="cage", taus=taus, print.taus=print.taus, B=B, nderivs=1,
average=1, alpha=alpha, process="pivotal", rearrange=FALSE, uniform=TRUE, se="unconditional", printOutput=TRUE, method="fn")

# Nonparametric series quantile regression Use npqr (quantreg.nonpar) With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished
