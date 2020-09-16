# Phylogeny
 progress for phd data analysis
start using MrBayes in 14092020
problem: converting fasta to nexus file
solution: use mesquite

#MrBayes command line
MrBayes > execute filename.nex
MrBayes > help #run in different prompt to see description in each commmand line
MrBayes > showmodel #to check model setting prior analysis
MrBayes > lset Nst = 6 Rates = Invgamma Ngammacat=4 #setting parameter of likelihood models
MrBayes > help prset #to set different prior setting according to what desire and the prior knowldege, leave it default if you have no prior knowledge
MrBayes > show model
MrBayes > help mcmc #check the default of mcmc analysis
MrBayes > mcmcp Ngen = 5000000 Nrun =2 mcmcdiagn = yes diagnfreq = 1000 relburnin=yes burninfrac=0.1 nchain=6 samplefreq=500 Printfreq = 1000
MrBayes > help mcmc #see if the parameter has changes
MrBayes > mcmc #run the mcmc analysis
MrBayes > sump #to summarized sample parameter
MrBayes > sumt #to summarized the tree parameter
