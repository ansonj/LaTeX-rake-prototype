# Set to false if your paper is in Dropbox or similar
# and the sync service can't keep up
$clean_automatically = true

# Delete this line or set to nil if not interested
$target_length = 10..15

desc 'Default task (process with BibTeX)'
task :default => [:bibtex]

desc 'Remove intermediate files'
task :clean do
    func_clean
end

desc 'Open output pdf'
task :open do
    func_open
end

desc 'Process with BibTeX'
task :bibtex do
    func_run_dry
    func_run_bibtex
    func_run_dry
    func_run_create
    if $clean_automatically
        func_clean
    end
    func_open
    func_print_target
end

desc 'Process, but skip BibTeX'
task :nobib do
    func_run_dry
    func_run_create
    if $clean_automatically
        func_clean
    end
    func_open
    func_print_target
end

desc 'Quick recreate+open pdf'
task :quick do
    func_run_create
    func_open
end

def func_run_dry
    sh 'pdflatex -draftmode -halt-on-error master.tex'
end

def func_run_create
    sh 'pdflatex -halt-on-error master.tex'
end

def func_run_bibtex
    sh 'bibtex master'
end

def func_clean
    sh 'rm -f master.aux'
    sh 'rm -f master.log'
    sh 'rm -f master.out'
    sh 'rm -f master.toc'
    # bibtex stuff
    sh 'rm -f master.bbl'
    sh 'rm -f master.blg'
end

def func_open
    sh 'open ./master.pdf'
end

def func_print_target
    if $target_length != nil
        puts "Target length is #{$target_length.first}-#{$target_length.last} pages."
    end
end
