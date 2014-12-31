task :default => [ :tarball, :publish, :cleanup ]

task :tarball do
  sh "tar cjvf build/ansible-demo-tarball.tbz2 -C ./ --exclude 'build/*' ./*"
end

task :publish do
  sh "aws s3 cp --acl public-read ../ansible-demo-tarball.tbz2 s3://sps-build-deploy/ansible/ansible-demo-tarball.tbz2"
end

task :cleanup do
  sh "rm build/ansible-demo-tarball.tbz2"
end
