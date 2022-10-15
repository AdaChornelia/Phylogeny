# Phylogeny
## RE-EDIT A WHOLE OF THIS MESS

progress for phd data analysis
start using MrBayes in 14092020
problem: converting fasta to nexus file
solution: use mesquite

#MrBayes command line
begin mrbayes;
MrBayes > execute filename.nex
MrBayes > help #run in different prompt to see description in each commmand line
MrBayes > showmodel #to check model setting prior analysis
MrBayes > lset Nst = 6 Rates = Invgamma Ngammacat=4 #setting parameter of likelihood models
MrBayes > help prset #to set different prior setting according to what desire and the prior knowldege, leave it default if you have no prior knowledge
MrBayes > show model
MrBayes > help mcmc #check the default of mcmc analysis
MrBayes > mcmcp Ngen = 5000000 Nrun =2 mcmcdiagn = yes diagnfreq = 1000 relburnin=yes burninfrac=0.1 nchain=6 temp=0.5 samplefreq=500 Printfreq = 1000
MrBayes > help mcmc #see if the parameter has changes
MrBayes > mcmc #run the mcmc analysis
MrBayes > sump #to summarized sample parameter
MrBayes > sumt #to summarized the tree parameter
end;


#MrBayes try run 1-mesquite insert command line in dataset
begin mrbayes;
	set autoclose=yes nowarn=yes;
	lset nst=6 rates=invgamma;
	unlink statefreq=(all) revmat=(all) shape=(all) pinvar=(all);
	prset applyto=(all) ratepr=variable;
	mcmcp ngen= 10000000 relburnin=yes burninfrac=0.25 printfreq=1000  samplefreq=1000 nchains=4 savebrlens=yes;
	mcmc;
	sumt;
end;

#run MrBayes2 21092020 11.30am
execute nex from mesquite with all parameters was deleted
commandline as follow:
begin MrBayes
  execute rhinoformrbayes2.nex
  lset nst = 6 rates=invgamma ngammmacat=4
  showmodel
  mcmcp ngen=5000000 nrun=2 mcmcdiagn=yes diagnfreq=1000 relburnin=yes burninfrac=0.1 nchain=5 temp=0.5 samplefreq=500 printfreq=1000
  help mcmc
  mcmc
end,
#done by 24092020
