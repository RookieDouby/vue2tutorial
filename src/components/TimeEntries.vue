<template>
	<div>
		<router-link
			v-if="$route.path !== '/time-entries/log-time'"		
			to="/time-entries/log-time"
			class="btn btn-default"
		>
		</router-link>
		<div v-if="$route.path === '/time-entries/log-time'">
			<h3>创建</h3>
		</div>
		<hr>

		<router-view></router-view>

		<div class="time-entries">
			<p v-if="!plans.length">
				<strong>还没有任何计划</strong>
			</p>
			<div class="list-group">
				<a class="list-group-item" v-for="(plan,index) in plans">
					<div class="row">
						<div class="col-sm-2 user-details">
							<img :src="plan.avatar" class="avatar img-circle img-responsive">
							<p class="text-center">
								<strong>
									{{ plan.name }}
								</strong>
							</p>
						</div>
					</div>
				</a>
			</div>
		</div>
	</div>
</template>